# python 03
> 뇌를 자극하는 파이썬 3 - 박상현
## 오류를 어떻게 다뤄야 할까
> Contents
>
> * 예외란
> * try ~ except로 예외 처리하기
>   * 복수 개의 except절 사용
>   * try절을 무사히 실행하면 만날 수 있는 else
>   * 어떤 일이 있어도 반드시 실행되는 finally
> * Exception 클래스
> * 우리도 예외 좀 일으켜 보자
> * 내가 만든 예외 형식
### 예외란
* 파이썬에서 Exception은 문법적으로는 문제가 없는 코드를 실행하는 중에 발생하는 오류
  * ValueError
```python
def my_power(y):
    print('숫자를 입력하세요')
    x = input()
    return int(x) ** y
if __name__ == '__main__':
    print(my_power(2))
```
```python
숫자를 입력하세요
a
Traceback (most recent call last):
  File "C:\NJ\workspace\0426\exception\value_error.py", line 8, in <module>
    print(my_power(2))
  File "C:\NJ\workspace\0426\exception\value_error.py", line 4, in my_power
    return int(x) ** y
ValueError: invalid literal for int() with base 10: 'a'
```
### try ~ except로 예외 처리하기
* try 절 안에는 문제가 없을 경우의 코드 블록을 배치
* except 절에는 문제가 생겼을 때 처리하는 코드 블록을 배치
```python
try:
    # 문제가 없을 경우 코드 블록
except:
    # 문제가 생겼을 때 실행할 코드
```
* ex
```python
try:
    s1 = input()    
    s2 = input()
    print(int(s1) + int(s2))
except:
        print('숫자를 입력하세요')
```
* 복수의 except절로 처리
```python
try:
    s1 = input()    
    s2 = input()
    print(int(s1) / int(s2))
except ValueError:
    print('숫자를 입력하세요')
except ZeroDivisionError:
    print('0으로 나눌 수 없습니다')
```
* 반복문에서 try ~ except 처리
```python
ar1 = [10, 20, 30]
ar2 = [5, 0]
for i in range(len(ar1)):
    try: 
        print(ar1[i] / ar2[i])
    except ZeroDivisionError:
        
        
        print('0으로 나눌 수 없습니다.')
    except:
        print('나누는 데이터가 부족합니다.')
```
```python
ar1 = [10, 20, 30]
ar2 = [5, 0]
for i in range(len(ar1)):
    try: 
        print(ar1[i] / ar2[i])
    except ZeroDivisionError as err:
        print(err)
    except IndexError as err:
        print(err)
```
```shell
2.0
division by zero
list index out of range
```
* try절을 무사히 실행하면 만날 수 있는 else
```python
try:
    #
except:
    #
else:
    # except절을 만나지 않았을 경우 실행하는 코드 블록
```