## Python - Positional Argument

- 위치 인수란 함수에 인수를 순서대로 넣는 방식을 말한다.
  인수의 위치가 정해져있기 때문에 이를 이용해서 여러 기법을 사용할 수 있다.

- 리스트 또는 튜플의 언패킹을 사용해서 위치 인수를 활용할 수 있다.
  리스트와 튜플의 언패킹은 리스트와 튜플의 앞에 *을 넣어주는 식으로 작동된다.
  그러면 리스트와 튜플의 요소 하나하나가 매개변수에 매칭되어 들어간다.

  ```python
  def pa(a, b, c):
      print(a, b, c)
      
  l = [1, 2, 3]
  t = [4, 5, 6]
  
  pa(*l)
  pa(*t)
  
  # 1 2 3
  # 4 5 6
  ```

- 이 언패킹을 이용해서 가변 인수 함수를 만들 수 있다.
  가변 인수는 매개변수 중 가장 오른쪽에 위치해야하며
  몇 개가 들어올지 모른다.
  가변 인수를 만들기 위해서는 매개변수 앞에 *을 붙여주면 된다.

  ```python
  def test(*args):
      for arg in args:
          print(arg)
  
  test(1, 2, 3)
  
  # 1
  # 2
  # 3
  ```

- 이렇게 만들어진 가변 인수는 반복문을 통해 사용할 수 있다.