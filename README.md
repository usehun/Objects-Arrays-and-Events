## Objects-Arrays-and-Events

#### (1)
  const h2 = document.querySelector(“h2”);
  가장 먼저 h2태그를 js에서 사용할 수 있도록 선언해 줍니다. querySelector로 태그명을 사용해 가져오기 때문에 css 선택자를 사용하지 않습니다.
  <br/>

#### (2)
  먼저 마우스가 h2 위에 있을 경우에 동작할 handleEnter함수를 선언합니다.
  <br/>
  텍스트를 변경하기 위해 h2객체의 innerText프로퍼티를 사용할 수 있습니다. 위 코드와 같이 innerText에 "The mouse is here!"을 넣어 줍니다.
  <br/>
  텍스트의 색을 변경하기 위해서는 h2객체의 프로퍼티인 style객체에서 color프로퍼티를 사용합니다. 색상은 colors배열에서 인덱스 값을 통해 선택해 줍니다. 인덱스 값은 0부터 시작하므로 위 코드는 배열의 첫 번째 요소를 선택한 것입니다.
  <br/>
  ![ex01](https://user-images.githubusercontent.com/88027485/193195965-1e2ed89e-4c06-45e0-910a-8c6a63c66d95.png)

#### (3)
  위 방법과 같이 handleLeave, handleResize, handleSelect, handleContext 함수도 작성합니다. 함수들은 모두 superEventHandler객체 내부에 작성해야 합니다.
  (이렇게 객체 내부에 선언한 함수를 메서드라 합니다.)
  <br/>
  2번의 사진은 객체 내부에 함수를 선언할 때 사용하는 문법으로 작성되어 있습니다.

#### (4)
  h2.addEventListener("mouseenter", superEventHandler.handleEnter);
  <br/>
  작성한 함수를 사용해 이벤트 핸들러를 등록합니다. addEventListener메서드를 사용합니다. h2에 mouseenter이벤트가 발생할 때 superEventHandler객체의 handleEnter메서드가 실행되어야 합니다.

#### (5)
  위와 같이 다른 이벤트 핸들러도 등록해 줍니다.
  <br/>
  이때 resize와 contextmenu이벤트는 h2가 아닌 Window에서 발생하므로 이벤트 타깃을 Window로 작성합니다.
