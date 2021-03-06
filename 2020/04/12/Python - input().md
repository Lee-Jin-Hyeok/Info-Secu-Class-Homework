## Python - input()

- 기존에는 변수에 값을 임의로 설정해주었다.
  하지만 실제로는 사용자에게 임의의 수를 할당받는 방법을 쓰는 경우가 훨씬 많을 것이다.
  따라서 파이썬에서는 input() 함수를 제공한다.

- input() 함수는 매개변수로 str 값을 받을 수 있으며 리턴값이 str 값이다.
  매개변수로 받은 str 값은 입력을 하기 전에 출력해줌으로서
  어떤 입력을 행해야하는지 알려주는 용도로 사용할 수 있다.
  리턴값은 항상 문자열이기 때문에 계산시에 잘 생각해야한다.

- 만약 리턴값을 정수로 사용하기 위해서는 int()를, 실수로 사용하기 위해서는 float()를 사용해서
  형변환을 시켜줘야 문자열이 아닌 정수의 값을 사용할 수 있다.

- 다음은 input() 함수를 이용해서 계산하는 코드이다.

  ```python
  a = int(input('첫 번째 값을 입력해주세요 : '))
  b = int(input('두 번째 값을 입력해주세요 : '))
  
  print(a + b)
  
  # 첫 번째 값을 입력해주세요 : 10
  # 두 번째 값을 입력해주세요 : 20
  # 30
  ```

- 그리고 print() 함수는 자동 개행을 진행하지만 input() 함수에 의해서 출력되는 문자열은
  자동 개행이 되지 않는다.



#### split()

- input() 함수에 이어서 split() 함수를 이용하면 한 줄에 여러 입력을 받을 수 있다.
  그렇게 두 개 이상의 값을 받는 방법은 다음과 같다.

- split() 함수의 매개변수로 아무것도 주지 않으면 공백을 기준으로 나눠서 입력받고
  매개변수로 문자열을 주면 그 문자열을 기준으로 나눠서 입력받는다.

  ```python
  a, b, c = input('입력 : ').split()
  print(a)
  print(b)
  print(c)
  
  # 입력 : 1 2 3
  # 1
  # b
  # c
  ```

- 만약 입력된 값에 의해서 나오는 문자열의 수와 받는 리턴값의 수가 다르면 오류를 발생시킨다.

- split() 함수를 이용하면 int()를 사용할 수 없기 때문에 결과가 나온 뒤 하나하나 바꿔주어야 한다.

  ```python
  a, b, c = input('입력 : ').split(',')
  a = int(a)
  b = int(b)
  c = int(c)
  
  print(a + b + c)
  
  # 입력 : 1,2,3
  # 6
  ```

- 이것이 불편한 나머지 map() 함수를 이용해서 모두 형변환을 시킬 수 있다.
  map() 함수의 첫 번째 매개변수로 변환할 자료형을 넣고, 두 번째 매개변수로 input().split()를 넣는다.
  다음은 그의 예제이다.

  ```python
  a, b, c = map(int, input('입력 : ').split(','))
  print(a + b + c)
  
  # 입력 : 1,2,3
  # 6
  ```

  