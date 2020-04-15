## Python - Set

- 파이썬에서는 세트 자료형을 지원한다.
  세트는 수학에서의 집합을 뜻하는 것으로 다른 언어의 Set 자료형과 비슷한 기능을 가지고 있다.

#### 1. 세트 생성하기

- 세트는 중괄호를 사용하며 딕셔너리와는 다르게 키-값이 아닌 값만이 존재한다.

  ```python
  name = {'lee', 'kim', 'park'}
  print(name)
  
  # {'lee', 'kim', 'park'}
  ```

- 세트는 중복이 되지 않고 대괄호 인덱스를 이용해서 접근할 수 없다.

  ```python
  name = {'lee', 'kim', 'kim', 'lee', 'park'}
  print(name)
  # print(name[0]) # error
  
  # {'lee', 'kim', 'park'}
  ```

- 위에서는 순서가 지켜졌지만 실제로는 순서를 고려하지 않는다.

- in과 not in을 이용해서 요소가 존재하는지 알아볼 수 있다.

  ```python
  name = {'lee', 'kim', 'park'}
  print('lee' in name)
  print('son' not in name)
  
  # True
  # True
  ```

#### 2. set() 함수를 이용해서 세트 생성하기

- set() 함수의 매개변수에 반복가능한객체를 주면 그 객체를 기준으로 세트를 생성한다.

  ```python
  munja = set('python')
  print(munja)
  
  # {'p', 'y', 't', 'h', 'o', 'n'}
  
  empty = set()
  print(empty)
  
  # set()
  ```

- 비어있을 경우에는 set() 과 같이 표현한다.
  만약 세트를 {}으로 생성하면 빈 딕셔너리가 생성되므로 조심해야 한다.

- 만약 매개변수의 문자열에 같은 문자가 있으면 삭제한다.

#### 3. 세트 안에 세트 넣기

- 세트 안에 세트를 넣을 수 없다.

#### 4. 프로즌 세트

- 프로즌 세트 (frozenset)는 세트와 사용하는 방법은 같으나 변경할 수 없는 특징을 가지게 된다.
  삭제 및 연산, 삽입 등의 기능을 사용할 수 없다.

  ```python
  print(frozenset(range(10)))
  
  # frozenset({0, 1, 2, 3, 4, 5, 6, 7, 8, 9})
  ```

#### 5. 세트로 집합 연산하기

- 세트로 사용할 수 있는 집합으로는 합집합(union), 교집합(intersection), 차집합(difference),
  대칭차집합(symmetric difference)가 존재한다.

  ##### 5-1. 합집합(union) 연산하기

  - 합집합은 두 개의 집합이 있을 때 모든 요소를 합치는 연산입니다.
    만약 겹치는 요소가 있다면 하나만 적용됩니다.

  - 파이썬에서는 이 합집합을 OR 연산자인 '|'을 사용하거나 set.union() 메소드를 사용합니다.

    ```python
    a = {'a', 'b', 'c'}
    b = {'c', 'd', 'e'}
    print(a|b)
    print(set.union(a, b))
    
    # {'a', 'b', 'c', 'd', 'e'}
    # {'a', 'b', 'c', 'd', 'e'}
    ```

  ##### 5-2. 교집합(intersection) 연산하기

  - 교집합은 두 개의 집합이 있을 때 두 집합간의 겹치는 요소만 남기는 연산입니다.

  - 파이썬에서는 이 교집합을 AND 연산자인 '&'을 사용하거나 set.intersection() 메소드를 사용합니다.

    ```python
    a = {'a', 'b', 'c'}
    b = {'c', 'd', 'e'}
    print(a&b)
    print(set.intersection(a, b))
    
    # {'c'}
    # {'c'}
    ```

  ##### 5-3. 차집합(difference) 연산하기

  - 차집합은 두 집합이 있을 때 하나의 집합의 요소에서 다른 하나의 집합의 요소를 모두 빼는 연산입니다.

  - 파이썬에서는 이 차집합을 뺄셈 연산자인 '-'을 사용하거나 set.difference() 메소드를 사용합니다.

    ```python
    a = {'a', 'b', 'c'}
    b = {'c', 'd', 'e'}
    print(a-b)
    print(set.difference(a, b))
    
    # {'a', 'b'}
    # {'a', 'b'}
    ```

  ##### 5-4. 대칭차집합(symmetric difference) 연산하기

  - 대칭차집합은 A 집합에서 B 집합의 요소를 뺀 집합과 B 집합에서 A 집합의 요소를 뺀 집합을
    합집합 연산하는 연산입니다.

  - 파이썬에서는 이 대칭차집합을 XOR 연산자인 '^'을 사용하거나 set.symmetric_difference() 메소드를
    사용합니다.

    ```python
    a = {'a', 'b', 'c'}
    b = {'c', 'd', 'e'}
    print(a^b)
    print(set.symmetric_difference(a, b))
    
    # {'a', 'b', 'd', 'e'}
    # {'a', 'b', 'd', 'e'}
    ```

#### 6. 집합 연산 후 할당 연산자

- +=, -=, %=, /=, *=와 같은 복합 대입 연산자들이 존재한다.
  이러한 연산자 말고도 집합 연산인 |, &, -, ^ 연산자들이 존재한다.
  이러한 연산자들도 복합 대입 연산자처럼 사용할 수 있다.
  하지만 비트 연산자와 비슷하므로 피연산자 두 개가 모두 세트일 경우에만 사용 가능합니다.

  ##### 6-1. 합집합 대입 연산자

  - 합집합 후 대입(할당)을 하는 연산자는 |=이다.
    사용하는 방법은 다른 복합 대입 연산자와 같다.

  - update() 메소드와 같은 역할을 한다.

    ```python
    a = {1, 2}
    a |= {3}
    print(a)
    
    # {1, 2, 3}
    
    b = {1, 2}
    b.update({3})
    print(b)
    
    # {1, 2, 3}
    ```

  ##### 6-2. 교집합 대입 연산자

  - 교집합 후 대입을 하는 연산자는 &= 이다.

  - intersection_update() 메소드와 같은 역할을 한다.

    ```python
    a = {1, 2, 3, 4}
    a &= {1, 2, 3}
    print(a)
    
    # {1, 2, 3}
    
    b = {1, 2, 3, 4}
    b.intersection_update({1, 2, 3})
    print(b)
    
    # {1, 2, 3}
    ```

  ##### 6-3. 차집합 대입 연산자

  - 차집합 후 대입을 하는 연산자는 -= 이다.

  - difference_update() 메소드와 같은 역할을 한다.

    ```python
    a = {1, 2, 3, 4}
    a -= {4, 5, 6}
    print(a)
    
    # {1, 2, 3}
    
    b = {1, 2, 3, 4}
    b.difference_update({4, 5, 6})
    print(b)
    
    # {1, 2, 3}
    ```

  ##### 6-4. 대칭차집합 대입 연산자

  - 대칭차집합 후 대입을 하는 연산자는 ^= 이다.

  - symmetric_difference_update() 메소드와 같은 역할을 한다.

    ```python
    a = {1, 2, 3}
    a ^= {3, 4, 5}
    print(a)
    
    # {1, 2, 4, 5}
    
    a = {1, 2, 3}
    a.symmetric_difference_update({3, 4, 5})
    print(a)
    
    # {1, 2, 4, 5}
    ```

#### 7. 부분 집합과 상위 집합

- 부분 집합은 B 집합에 있는 모든 요소가 A 집합에도 있을 때 B집합을 A 집합의 부분 집합이라고 한다.

- 파이썬에서 부분 집합을 알아내는 방법은 <= 연산자를 사용하거나 issubset() 메소드를 사용하면 된다.

  ```python
  a = {1, 2, 3, 4}
  print(a <= {1, 2, 3, 4})
  
  # True
  ```

- 진 부분 집합인지도 확인할 수 있는데 진 부분 집합은 부분 집합인데 완전히 같은 세트가 아닐 때를 말한다.

- 파이썬에서는 진 부분 집합을 < 연산을 통해서 알아낼 수 있다.

  ```python
  a = {1, 2, 3, 4}
  print(a < {1, 2, 3, 4})
  
  # False
  ```

- 상위 집합은 부분 집합과 반대 개념이다.
  상위 집합은 >= 연산, 또는 issuperset() 메소드를 통해서 알아 낼 수 있다.
  마찬가지로 진 상위 집합은 > 연산을 통해서 알아 낼 수 있다.

  ```python
  a = {1, 2, 3, 4}
  print(a >= {1, 2, 3, 4})
  print(a > {1, 2, 3, 4})
  
  # True
  # False
  ```

#### 8. 같은 세트인지 확인하기

- 같은 세트인지 확인하는 방법은 == 연산자를 통해서 쉽게 알아낼 수 있다.
  다른지 확인하는 방법은 != 연산자를 사용하면 된다.

  ```python
  a = {1, 2, 3, 4}
  b = {1, 2, 3, 4}
  print(a == b)
  
  # True
  ```

#### 9. 세트의 요소가 겹치지 않는지 확인하기

- 하나의 세트와 다른 하나의 세트의 요소가 모두 겹치지 않는지 확인하는 방법은
  isdisjoint() 메소드를 사용하면 된다.

  ```python
  a = {1, 2, 3}
  b = {4, 5, 6}
  c = {3, 4, 5}
  
  print(a.isdisjoint(b))
  print(a.isdisjoint(c))
  
  # True
  # False
  ```

#### 10. 세트 요소 추가하기

- add() 메소드를 이용하면 세트에 요소를 추가할 수 있다.
  매개변수로 세트의 요소를 받는다.

  ```python
  a = {1, 2, 3, 4}
  a.add(5)
  print(a)
  
  # {1, 2, 3, 4, 5}
  ```

#### 11. 세트 요소 삭제하기

- 세트에서 요소를 삭제하는 방법은 총 네 가지가 있다.
  remove(), discard(), pop(), clear() 메소드를 사용할 수 있다.

  ##### 11-1. remove() 메소드 사용하기

  - remove() 메소드는 매개변수로 삭제할 요소를 받아서 매개변수로 된 요소가 있으면 삭제하고
    없으면 오류를 발생시킨다.

    ```python
    a = {1, 2, 3}
    a.remove(3)
    print(a)
    
    # a.remove(4) # error
    
    # {1, 2}
    ```

  ##### 11-2. discard() 메소드 사용하기

  - discard() 메소드는 add() 메소드와 동일하게 작동하지만 없는 요소를 매개변수로 받았을 경우에
    아무일도 일어나지 않는다.

    ```python
    a = {1, 2, 3}
    a.discard(3)
    print(a)
    a.discard(4)
    print(a)
    
    # {1, 2}
    # {1, 2}
    ```

  ##### 11-3. pop() 메소드 사용하기

  - pop() 메소드는 매개변수를 받지 않아서 랜덤으로 요소를 하나 삭제하여 리턴한다.
    만약 요소가 없을 경우에 에러를 발생시킨다.

    ```python
    a = {1, 2, 3}
    print(a.pop())
    print(a.pop())
    print(a.pop())
    
    # 2
    # 3
    # 1
    ```

  ##### 11-4. clear() 메소드 사용하기

  - clear() 메소드는 세트에 존재하는 모든 요소를 삭제하는 메소드이다.

    ```python
    a = {1, 2, 3}
    a.clear()
    print(a)
    
    # set()
    ```

#### 12. 세트의 요소 개수 구하기

- 세트의 요소 개수를 구하려면 len() 함수를 사용하면 된다.

  ```python
  a = {1, 2, 3}
  print(len(a))
  
  # 3
  ```

#### 13. 세트 복사

- 세트를 복사할 경우 그냥 대입연산을 하면 같은 세트를 가리키기 때문에 어떤 하나의 세트의 요소를 변경하면
  다른 세트의 요소도 같이 변경됩니다.
  따라서 깊은 복사를 하기 위해서 copy() 메소드를 사용합니다.

  ```python
  a = {1, 2, 3}
  b = a
  a.add(4)
  print(a)
  print(b)
  
  # {1, 2, 3, 4}
  # {1, 2, 3, 4}
  
  a = {1, 2, 3}
  b = a.copy()
  a.add(4)
  print(a)
  print(b)
  
  # {1, 2, 3, 4}
  # {1, 2, 3}
  ```

- 세트안에는 세트를 넣을 수 없기 때문에 deepcopy() 메소드는 지원하지 않습니다.

#### 14. 세트와 반복문

- 세트를 반복문 안에 넣어서 요소를 출력하게 하는 방법은 간단하다.
  어차피 딕셔너리처럼 키-값으로 되어 있는 것도 아니고 값밖에 없기 때문에 인덱스도 하나밖에 필요없다.

  ```python
  a = {1, 2, 3}
  for i in a:
      print(i)
      
  # 1
  # 2
  # 3
  ```

- 물론 순서를 유지하지 않기 때문에 어떤 값이 먼저 나올지는 모른다.

#### 15. 세트 표현식

- 세트 표현식은 다른 딕셔너리와 리스트, 튜플과 같다.

  ```python
  a = {i for i in 'python' if i != 't'}
  print(a)
  
  # {'p', 'y', 'h', 'o', 'n'}
  ```

- 물론 순서는 다를 수 있다.