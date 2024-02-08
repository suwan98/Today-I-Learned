# forwarRef

## forwarRef란?

- 커스텀컴포넌트에서 ref를 전달할때 일반적으로 태그에 ref를 전달하듯이 ref를 전달할 수 없다.
- 그러나 forwardRef 함수를 통해 커스텀컴포넌트에 대한 ref를 전달할 수 있다.

```jsx
/* 커스텀 컴포넌트인 Input은 ref를 props로 넘겨줄 수 없다.*/
<Input type="text" ref={titleRef} label="제목" />
```

## 사용방법

**사용하고자 하는 커스텀 컴포넌트를 forwarRef로 래핑하고 두번째 인자로 전달받고자 하는 ref를 props로 정의한다.**

```jsx
import {forwardRef} from "react";

function Input({label, textarea, ...props}, ref) {
  const classes =
    "w-full p-1 border-b-2 rounded-sm border-stone-300 bg-stone-200 text-stone-600 focus:outline-none focus:border-stone-600";

  return (
    <p className="flex flex-col gap-1 my-4">
      <label className="text-sm font-bold text-stone-500">{label}</label>
      {textarea ? (
        <textarea ref={ref} className={classes} {...props} />
      ) : (
        <input ref={ref} className={classes} {...props} />
      )}
    </p>
  );
}

export default forwardRef(Input);
```
