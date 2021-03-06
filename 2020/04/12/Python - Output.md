## Python - Output

#### 1. 여러 개 출력하기

- print() 함수를 사용할 때 한 번에 여러 개의 출력을 할 수 없을까?
  print() 함수안에 콤마와 공백으로 구분지어서 여러 개를 출력할 수 있도록 지원한다.
  물론 콤마는 반드시 존재해야하며 공백은 부가적인 것이다.
  다음은 print() 함수를 이용해서 여러 개를 출력하는 예제이다.

  ```python
  print(1, 2, 3)
  print('Hello', 'World')
  x = 1.1
  y = 2.2
  print(x, y)
  
  # 1 2 3
  # Hello World
  # 1.1 2.2
  ```

- 이렇게 출력시에 공백 하나로 구분지어서 출력하게 된다.

  ##### 1-1 sep

  - print() 함수의 속성 중에서 sep 속성을 변경함으로서
    print() 함수에 의해서 출력되는 구분자를 변경할 수 있다.

    ```python
    print(1, 2, 3, sep=', ')
    
    # 1, 2, 3
    ```

  - 만약 출력의 갯수가 하나라면 sep 속성을 지정해도 아무 효과가 없다.

    ```python
    print(1, sep='xxxxxxxxxxx')
    
    # 1
    ```

  ##### 1-2 end

  - print() 함수의 끝에는 반드시 개행이 된다는 것을 알고 있을 것이다.
    이 개행은 암묵적으로 end라는 값이 '\n'이기 때문이다.
    print() 함수의 출력 끝에는 end의 값을 같이 출력한다.

    ```python
    print(1, 2, 3, end='')
    print(1, 2, 3, end='')
    
    # 1 2 31 2 3
    ```

  - sep과 end를 동시에 사용하기 위해서는 end를 먼저 쓰고 sep을 써야 한다.
    만약 이 두 개의 키워드의 순서가 바뀌면 오류를 발생시킨다.

    ```python
    print(1, 2, end='', sep=', ')
    print(3, 4, end='', sep=', ')
    
    # 1, 23, 4
    ```