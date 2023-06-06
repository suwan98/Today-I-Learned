<h1> &ltaddress&gt : 주소 요소(그룹핑 요소) </h1>

<br />

> **adress 요소의 정의 ✍️**

**사용자 및 조직, 단체 등의 주소 및 연략처 정보**를 마크업할 때 사용 <br/>
`footer` 태그로 묶어 **본문 footer**에 주로 쓰인다

```html
<address>
    <span>(주)멋쟁이사자처럼</span>
    <span>대표이사 이두희</span>
    <span>서울특별시 종로구 종로3길 17 D타워, 16-17층</span>
    <span>사업자 등록번호 : 264-88-01106</span>
    <span>통신판매업 신고 : 2019 - 서울강남 - 00774</span>
    <span>연락처 : 
        <a href="tel:+821012345678">010-1234-5679</a>
    </span>
    <span>문의
        <a href="mailto:contact@likelion.net">contact@likelion.net</a>
    </span>
</address>
```

**`<a href="tel:+821012345678"> 속성:` 해당 링크를 클릭 시 전화를 걸 수 있다**

 **`<a href="mailto:contact@likelion.net">` 속성 : 링크 클릭 시 이메일 주소 미리 세팅**