## Python - Static Method, Class Method

- 파이썬에는 정적 메소드와 클래스 메소드가 나뉘어져 있습니다.
  둘 다 클래스의 인스턴스 생성 없이 사용할 수 있는 메소드라는 것은 같습니다.
  하지만 다른 점이 조금 존재합니다.
- 정적 메소드는 클래스 속성에 접근할 수 없습니다.
  하지만 클래스 메소드는 첫 번째 매개변수로 cls를 받기 때문에
  이를 이용해서 클래스 속성에 접근할 수 있습니다.

- 정적 메소드는 메소드 위에 데코레이터로 @staticmethod가 붙고
  클래스 메소드는 메소드 위에 데코레이터로 @classmethod가 붙습니다.
- 둘다 self를 받지 않기 때문에 인스턴스 속성이나 인스턴스 메소드를 사용할 수 없습니다.