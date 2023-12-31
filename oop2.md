## 상속보단 조립  
### 상속  
상위 클래스의 기능을 재사용하고, 확장할 수 있음.  
  
**상속의 단점**  
1) 하위 클래스가 생기면 상위 클래스를 변경하기 어려워짐: 모든 하위 클래스에 영향을 주므로 함부로 바꿀 수 없음.  
2) 클래스 수가 증가함: 약간씩 다른 기능 때문에 클래스를 하나 더 만들어 줘야 하는 상황 발생.  
3) 상속을 오용할 수 있음: 예를 들면, 최상위 클래스에 add라는 클래스가 있고, 그것을 상속받은 클래스에 put이라는 메소드가 있다. add 메소드는 배열에 요소를 추가한다. put을 add 메소드를 이용해서 배열에 요소를 추가하고, currentSize를 1 증가한다. 즉 추가되는 요소의 수를 currentSize가 정상적으로 반영되려면 put만을 활용해야 한다. 하지만 사용자 입장에서는 오해해서 add를 사용할 수도 있다. 하위 클래스에서는 조부모, 부모 클래스에 모두 똑같이 접근이 가능하기 때문이다.  
  
=> 이런 단점을 해결하기 위해 조립을 활용한다  
  
### 조립  
여러 객체를 결헙하여 사용해서 더 복잡한 기능을 제공한다. 보통 필드로 참조하는 다른 객체를 참조하는 방식으로 조립하거나, 필요한 시점에 객체를 생성하여 이용한다.  
   
**조립의 장점**  
1) 하위 클래스가 안 만들어지니 이후 수정도 상대적으로 용이해진다.  
2) 상속을 애초에 안 하니 오용할 일이 없다.  
  
**결론**  
상속하기에 앞서 조립으로 풀 수 없는지 검토한다.   
진짜 하위 타입인 경우에만 상속을 이용한다.  
   

### 기능과 책임 분리
하나의 기능은 여러 하위 기능으로 분리할 수 있다.   
ex. 암호 변경 기능은 변경 대상 확인 / 대상 암호 변경으로 쪼개질 수 있다.  
기능을 분리하여 여러 객체에 어떻게 책임을 분배할지가 객체지향의 핵심  
하나의 클래스와 메서드가 커지면 절차 지향때와 같이 유지보수에 어려움을 겪게 된다.  

**책임 분리 방법**  
1. 디자인 패턴 적용: 이미 만들어진 디자인 패턴을 활용한다.  
2. 계산 분리: 하나의 계산 로직을 별도의(calculator 같은) 객체로 분리한다.  
3. 연동 분리: 네트워크, 메시징, 파일 등 외부 연동 코드를 별도 클래스로 분리한다.  
4. 조건 분기 추상화: if else 구문은 객체 메서드로 대체 시도  
  
**역할 분리의 장점**
1. 테스트가 용이해짐    
2. 가독성이 좋아짐  
3. 확장이 용이해짐  
  
### 의존과 DI  