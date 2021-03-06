## Python - Tuple

- 튜플은 리스트이지만 변하지 않는 값들의 집합입니다.
  리스트와 다른 점은 변하지 않는다는 점 밖에 없기 때문에 서로 상호변환도 가능합니다.
  물론 안정성을 위해서 본체가 변하지 않고 새로운 리스트나 튜플이 생기는 방식입니다.

#### 1. 튜플 생성하기

- 튜플을 생성하는 방법은 리스트와 비슷합니다.
  리스트는 대괄호를 이용했지만 튜플은 소괄호를 이용한다.
  굳이 소괄호를 사용하지 않고 콤마로만 표현해도 문제될 것은 없다.

  ```python
  >>> intTuple = (1, 2, 3)
  >>> intTuple
  (1, 2, 3)
  >>> intTuple = 4, 5, 6
  >>> intTuple
  (4, 5, 6)
  ```

- 물론 리스트와 마찬가지로 자료형에 상관하지 않고 값을 저장할 수 있다.

  ```python
  >>> objTuple = (1, 1.1, 'Hello', True)
  >>> objTuple
  (1, 1.1, 'Hello', True)
  ```

#### 2. 빈 튜플 생성하기

- 빈 튜플을 생성하는 방법은 빈 리스트를 생성하는 방법과 같다.
  다만 리스트를 생성하는 대괄호가 아닌 튜플을 생성하는 중괄호라는 점이다.

  ```python
  >>> emptyTuple1 = ()
  >>> emptyTuple2 = tuple()
  >>> emptyTuple1
  ()
  >>> emptyTuple2
  ()
  ```

- 튜플은 중괄호를 생략해도 된다는 장점을 가지고 있었는데 빈튜플을 생성할 때는
  생략하게 되면 아무것도 남지 않는 공백이 되기 때문에 생략할 수 없다.

#### 3. range()를 이용해서 튜플 생성하기

- range() 함수를 이용해서 생성하는 것도 리스트와 마찬가지로 이루어진다.

  ```python
  >>> tuple1 = tuple(range(5))
  >>> tuple1
  (0, 1, 2, 3, 4)
  >>> tuple2 = tuple(range(3, 6))
  >>> tuple2
  (3, 4, 5)
  >>> tuple3 = tuple(range(5, -2, -1))
  >>> tuple3
  (5, 4, 3, 2, 1, 0, -1)
  ```

#### 4. 튜플과 리스트 상호변환하기

- 튜플을 이용해서 새로운 리스트를 생성할 수 있고
  리스트를 이용해서 새로운 튜플을 생성할 수 있다.

- list() 함수의 매개변수로 튜플을 넣어주거나 tuple() 함수의 매개변수로 리스트를 넣어주면
  새로운 리스트나 튜플의 생성이 가능하다.

  ```python
  >>> intList = [1, 2, 3]
  >>> intTuple = tuple(intList)
  >>> intTuple
  (1, 2, 3)
  >>> intList2 = list(intTuple)
  [1, 2, 3]
  ```

#### 5. 요소가 한 개인 튜플 생성하기

- 요소가 한 개인 튜플은 쉽게 생각하면 (n)과 같이 표현할 수 있을 것이다.
  하지만 소괄호를 생략하게 되는 튜플의 특성상 생략하면 n으로 일반 변수와 다른 것이 보이지 않는다.
  그렇기 때문에 구분을 해주기 위해서 변수 뒤에 콤마를 넣어준다.

  ```python
  >>> oneTuple1 = ('Hello',)
  >>> oneTuple2 = 'Hello',
  >>> oneTuple1
  ('Hello',)
  >>> oneTuple2
  ('Hello',)
  ```

#### 6. 튜플과 리스트 안의 문자열

- 튜플과 리스트 안에 문자열을 넣으면 문자열의 문자 하나하나를 분해하여 하나의 요소로 넣는다.
  다음의 예제를 살펴보자.

  ```python
  >>> strTuple = tuple('Hello')
  >>> strList = list('World')
  >>> strTuple
  ('H', 'e', 'l', 'l', 'o')
  >>> strList
  ['W', 'o', 'r', 'l', 'd']
  ```

- 이를 이용해서 사용하는 일이 많아질 것 같으니 꼭 기억하자

#### 7. 튜플 언패킹과 리스트 언패킹

- 튜플 언패킹과 리스트 언패킹은 튜플과 리스트의 요소를 여러 개의 변수에 할당하는 것을 말한다.

  ```python
  >>> intTuple = (1, 2, 3)
  >>> a, b, c = intTuple
  >>> print(a + b + c)
  6
  >>> intList = [4, 5, 6]
  >>> a, b, c = intList
  >>> print(a + b + c)
  15
  ```

- 참고로 변수에 리스트를 할당하는 것을 리스트 패킹, 튜플을 할당하는 것을 튜플 해킹이라고 한다.