# Nextjs에서의 이미지 최적화

## Next/Image 컴포넌트

- `Next` 설치 시 `Nextjs`는 기본적으로 `Image`라는 이름의 `Next` 고유의 컴포넌트 제공
- `Next/image` 컴포넌트에서 제공하는 대표적인 기능들은?
  - Lazy Loading
  - 이미지 사이즈 최적화
  - `placeHolder` 제공

### Lazy Loading

**`Next/image` 컴포넌트 사용 시 자동으로 `lazy-loading`이 적용된다**

- 이미지 일부에 `lazy loading`을 적용하고 싶지 않은 경우 해당 기능을 끌 수도 있음
  - `Image` 컴포넌트의 `priority`라는 `prop`을 `true`로 설정
  - `loading prop`에 `eager`값 설정

### 이미지 사이즈 최적화

**`Next/image`에서의 이미지 최적화**

- 디바이스 크기 별로 `srcSet`을 미리 지정, 사용자의 디바이스에 맞는 이미지를 다운로드 할 수 있도록 지원
- `layout prop` 설정에 따라 `srcSet` 목록이 변경된다
- `Nextjs`는 추가적으로 `webp`와 같은 용량이 작은 포맷으로 이미지를 변환해서 제공할 수 있다

### placeHolder

- `Nextjs`는 CLS로 인해 레이아웃이 흔들리는 현상을 방지하기 위해 `placeHolder`를 제공한다.
- 이미지가 로드되기 전에도 이미지 높이 만큼 영역을 표시해 이미지가 로드 된 후에 레이아웃이 흔들리지 않도록 조정
- `placeHolder`엔 빈 영역 또는 `blur`이미지등으로 커스텀하게 설정할 수 있다

## Image 컴포넌트 사용방법

**로컬 이미지의 경우**

- 로컬 이미지의 경우 빌드 시 `import`된 이미지 파일을 기준으로 자동으로 `width`, `height`가 지정되고, `base64`로 인코딩 된 `blur`이미지가 생성되어 별도의 작업 없이도 `placeholder=blur`를 적용할 수 있다

```jsx
import Image from "next/image";
import profilePic from "../public/me.png";

function Me() {
  return (
    <Image
      src={profilePic}
      alt="Picture of me"
      placeholder="blur" // Optional blur-up while loading
    />
  );
}
```

**리모트 이미지의 경우**

- 리모트 이미지일 경우 `Next.js`에 서빙하는 서버가 안전한 서버라고 `next.config.js`에 파일에 `CDN`의 `host`를 명시해야 한다

```js
module.exports = {
  images: {
    domains: ["your-cdn-image-domain"],
  },
};
```

- 사용법은 로컬이미지와 동일하고 `import`해서 이미지를 가져오는 대신 `src`에 해당하는 이미지 경로를 작성한다
- 로컬이미지와 달리 리모트 이미지는 빌드 시 이미지 파일에 접근하는 것이 불가능하므로 `width`/`height`값을 직접 설정하고
  - `blur` 이미 또한 생성되지 않는다 ❌
  - 이미지 로드 되기 전 `placeHoler`를 제공하고 싶다면 별도로 `blurDataURL` 속성에 `base64`로 인코딩 된 이미지 데이터를 작성해 줘야 한다.

```js
import Image from "next/image";

export default function Me() {
  return <Image src="/me.png" alt="Picture of me" width={500} height={500} />;
}
```

## Next/Image의 layout 속성

**Next/Image 컴포넌트에는 컨테이너 사이즈가 변경되었을 때 이미지 레이아웃이 어떻게 변경될지를 정할 수 있는 layout이라는 prop이 있다**

- intrinsic: default, 컨테이너 사이즈가 이미지 사이즈보다 작아졌을 때 컨테이너에 맞게 크기를 줄임
- fixed: (컨테이너 사이즈와 관계없이) 이미지 사이즈를 width, height 속성 값으로 고정
- responsive: 작은 컨테이너에서는 크기가 줄어들고, 큰 컨테이너에서는 크기가 늘어남(이미지 비율 유지)
- fill: relative 포지션을 가진 조상의 너비, 높이와 동일하게 조정함. 주로 objectFit 속성과 함께 사용
