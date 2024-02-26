# useImperativeHandle

## useImperativeHandle이란?

- `ref`로 노출되는 핸들을 사용자가 직접 정의하고 핸들리할 수 있는 Hook
- 컴포넌트의 최상위 레벨에서 useImperativeHandle 을 호출하여 노출할 ref 핸들을 사용자가 직접 정의할 수 있다.

### useImperativeHandle이 필요한 경우

- 일반적으로, 함수형 컴포넌트는 인스턴스를 가지지 않으므로 ref 속성을 사용할 수 없다.
  - 예를 들어, 부모 컴포넌트에서 자식 컴포넌트의 상태를 변경하거나, 자식 컴포넌트의 메서드를 호출해야하는 경우에 사용되게 된다.
  - 아래와 같이 useImperativeHandle와 forwarRef를 함께 사용하면, 부모 컴포넌트에서 자식 컴포넌트의 someFunction 메서드를 호출할 수 있게된다.
- 그러나 useImperativeHandle은 가능한 한 사용을 피하고, 대신 컴포넌트 상태를 상위로 끌어올리는(lifting state up) 등의 다른 방법을 사용하는 것이 좋다.
  - 그 이유는 코드의 가독성이 떨어질 수 있어 개발자가 이해하기 쉽지 않을 수 있다.

```jsx

/* 부모 컴포넌트 */

import React, { useRef, useEffect } from 'react';
import ChildComponent from './ChildComponent'; // 자식 컴포넌트를 가져옵니다.

function ParentComponent() {
  const childRef = useRef(); // Ref를 생성합니다.

  useEffect(() => {
    if (childRef.current) {
      childRef.current.someFunction(); // 자식 컴포넌트의 someFunction 메서드를 호출합니다.
    }
  }, []);

  return (
    <div>
      <ChildComponent ref={childRef} /> {/* Ref를 자식 컴포넌트에 연결합니다. */}
    </div>
  );
}

export default ParentComponent;


/* 자식 컴포넌트 */
import React, {useRef, useImperativeHandle} from "react";

function ChildComponent(props, ref) {
  useImperativeHandle(ref, () => ({
    someFunction: () => {},
  }));
}

export default React.forwardRef(ChildComponent);
```
