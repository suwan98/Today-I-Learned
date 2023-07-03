# Array.slice() vs splice() ✍️

> 이름도 비슷하고, 자꾸 쓸때마다 햇갈리는 배열메서드 두 메서드 <br/>
> 이번에야말로 두개의 차이점을 정확히 정리해보자 👨‍💻


## ✅ 1. Array.slice()


### 1.1 Array.slice() 메서드의 이해

- 먼저 코드를 먼저 보고 이해해보자!
  
  ```javascript
    const names = ["suwan", "minsoo", "seju", "James"];
    const names1 = names.slice(1);
    const names2 = names.slice(1, 2);
    const names3 = names.slice(-1);
    const names4 = names.slice(-1, 1);

    console.log(names1); // Array(3) ["minsoo", "seju", "James"]
    console.log(names2); // Array(1) ["minsoo"]
    console.log(names3); // Array(1) ["Jamse"]
    console.log(names4); // Array(0) []
  ```

  - `names.slice(1)`을 하니 `"suwan"`만 짤리고 나머지 배열이 나오네 ❓
  - `names.slice(1.2)`를 하니 `"minsoo"`만 나오네❓
  - `names.slice(-1)`를 하니 `"James"`만 나오네❓
  - `names.slice(-1, 1)`를 하니 모든배열이 없네❓
  
> 그럼 해당 코드에서 알 수 있는 것은❓

slice()의 첫번째 인자는 시작인덱스 (`start`) <br />
          두번째 인자는 끝인덱스 (`end`) 이구나~❗😀


<br />


### 1.2 Array.slice() 메서드의 정의

`slice()`는 배열로 부터 특정한 범위를 복사합 값들을 담고 있는 **새로운 배열**을 만드는데 사용한다
- 첫번째 인자로는 `시작 인덱스`

<br />

- 두번째 인자로는 `종료 인덱스`(option)을 받으며 => 0,부터 ~ 종료index 까지
  - 만약 `종료인덱스`를 부여하지 않는다면 원본의 배열이 끝날때 까지의 요소를 선택한다
- 인덱스부분에 음수 값을 부여하면, **배열의 끝**에서부터 요소를 선택한다
  - **음수의 값으로 인덱싱할 경우, 배열의 끝**에서부터 **요소**를 **선택**
- 시작인덱스부터 종료 인덱스까지의 값을 **복사하여 반환**한다

<br />

- 즉, 첫번째 `names1` 변수는 `slice(1)`만 지정했기때문에 첫번째 배열의 값인 ('suwan')만 빠지고, 나머지 배열이 반환되는 것이다

### 1.3 Array.slice() 메서드 정리

- `slice(a,b)` ==> **a인데스부터, b인덱스까지의 요소를 선택**해 **새로운배열을 생성**해줘 ❗
- Array.slice() 배열은 기존의 배열에 영향을 주지않고 새로운 배열을 생성해나간다❗ 


<br />
<hr />
<br />

## ✅ 2. Array.splice()

### 2.1 Array.splice() 메서드의 이해

- 먼저 코드를 먼저 보고 이해해보자!

```javascript
let months = ['Jan', 'March', 'April', 'June'];
months.splice(1, 0, 'Feb');
// ["Jan", "Feb", "March", "April", "June"] => 배열의 1번째 위치에 'Feb' 요소를 추가

months.splice(4, 1, 'May');
// ["Jan", "Feb", "March", "April", "May"] => 배열의 4번째 위치에 있는 'June'을 삭제하고 'May'요소를 추가

months.splice(3, 2);
// ["Jan", "Feb", "March"] => 배열의 3번째 위치부터 시작해 2개의 요소(April,May)를 삭제

```

<br />


> 그럼 해당 코드에서 알 수 있는 것은❓

`splice()` 메서드는 인자로 받은 인덱스를 **삭제** 및 **추가**하고 원본의 배열에도 영향을 주는 메서드이구나❗

<br />


### 2.2 Array.splice() 메서드의 정의

- `splice` 메서드란 원본 배열에 새로운 요소를 추가하거나 기존요소를 삭제 또는 교체하여 원본 배열을 변경 하고 **제거된 배열을 반환**

<br />


### 2.2.1 Array.splice() 메서드 구문

<br />


- `array.splice(start[, deleteCount[, item1[, item2[, ...]]]])`

<br />


- 첫번째 매개변수는 `start`
  - 배열의 변경을 시작할 index
  - 만약 배열의 길이보다 큰 값일 경우 배열의 길이로 설정된다
  - 음수일 경우 배열의 끝에서 부터 요소를 센다

<br />


- 두번째 매개변수는 `deleteCount`(option)
  - 배열에서 **제거할 요소의 수**
  - 생략가능하나 값이 첫번째 매개변수 `start`보다 크다면, **`start`부터의 모든 요소를 제거**한다

<br />

- 세번째 매개변수는 `item1,itme2,...`
  - 배열에 추가할 요소
  - 생략 시 요소를 제거하기만 한다

<br />


### 2.3 Array.splice() 메서드 정리

<br />


- `splice(a,b,c)` ==> a에서 시작해서 b인덱스에 있는 요소를 삭제하고 -> c 요소를 추가해라❗
- `splice()`메서드는 **원본의 배열에도 영향**을 주기 때문에 사용시에도 주의하고 사용해야한다 ❗

<br />
<hr />
<br />

## ✅ 3. Array.slice() 와 splice()의 차이점

<br />


- `Array.slice()`는 원본의 배열에 영향을 주지 않지만❗
  - `slice()`는 배열 복사가 생성되어 반환된 새 배열에만 영향을 주나, 원본배열을 변경하지 않는다

<br />

- `Array.splice()`는 원본의 배열에 영향을 준다❗
  - `splice()`메서드는 현재 배열을 변경하여 제거된 요소들을 반환한다


