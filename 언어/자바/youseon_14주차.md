## extends 와 implements 와 abstract 차이

- extends 
사실상 extends가 상속의 대표적인 형태다.
부모에서 선언 / 정의를 모두하여 자식은 메소드 / 변수를 그대로 사용할 수 있다.
'다중상속'을 지원하지 않는다.

- Implements (interface 구현)
부모 객체는 선언만 하며 정의(내용)은 자식에서 오버라이딩(재정의)해서 사용한다.
(extends가 못하는) 다중상속을 대신해준다.

- abstract
extends와 implements의 혼합, extends하되 몇 개는 추상 메서드로 구현되어 있다.
