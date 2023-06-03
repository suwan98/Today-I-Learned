**함수의 정의**


일련의 과정을 문(Statement)로 구현하고 **코드 블록으로 감싸서 하나의 실행단위로 정의한것**

함수는 이름과 매개변수를 가지며 필요할 때 호출하여 블록에 담긴 문들을 일괄적으로 실행 할 수 있게한다

```javascript
// 함수의 정의(함수 선언문)
function square(number) {
  return number * number;
}
```

여기서 함수의 정의만으로 함수가 실행되는것은 아닌데

`argument`를 `parameter`를 통해 함수에 전달하면서 함수의 실행을 **명시적으로 지시** 해야한다

이를 함수호출이라 함

```javascript
//함수의 호출
const result = square(2,5);

//함수 square에 인수 2,5를 전달하며 호출하면 반환값 10을 반환
console.log(result) // 10
```
<hr />

![](notion://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F3b7b33b6-680f-4d04-b607-9e1d10ab0431%2FUntitled.png?id=d5b2151d-ab94-478c-8b99-b7be167a1b48&table=block&spaceId=272b012a-e87d-473c-b817-b18213680590&width=2000&userId=eef98982-df9c-478f-954c-399253fd8658&cache=v2)

함수 내부로 **전달** 받는 변수 ⇒ **`매개변수(Parameter)`**

그에 대한 입력 ⇒ **`인수(Argument)`**

출력 ⇒ **`반환값(Return value)`**