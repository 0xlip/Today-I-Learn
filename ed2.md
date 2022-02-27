# python 03
> ���� �ڱ��ϴ� ���̽� 3 - �ڻ���
## ������ ��� �ٷ�� �ұ�
> Contents
>
> * ���ܶ�
> * try ~ except�� ���� ó���ϱ�
>   * ���� ���� except�� ���
>   * try���� ������ �����ϸ� ���� �� �ִ� else
>   * � ���� �־ �ݵ�� ����Ǵ� finally
> * Exception Ŭ����
> * �츮�� ���� �� ������ ����
> * ���� ���� ���� ����
### ���ܶ�
* ���̽㿡�� Exception�� ���������δ� ������ ���� �ڵ带 �����ϴ� �߿� �߻��ϴ� ����
  * ValueError
```python
def my_power(y):
    print('���ڸ� �Է��ϼ���')
    x = input()
    return int(x) ** y
if __name__ == '__main__':
    print(my_power(2))
```
```python
���ڸ� �Է��ϼ���
a
Traceback (most recent call last):
  File "C:\NJ\workspace\0426\exception\value_error.py", line 8, in <module>
    print(my_power(2))
  File "C:\NJ\workspace\0426\exception\value_error.py", line 4, in my_power
    return int(x) ** y
ValueError: invalid literal for int() with base 10: 'a'
```
### try ~ except�� ���� ó���ϱ�
* try �� �ȿ��� ������ ���� ����� �ڵ� ����� ��ġ
* except ������ ������ ������ �� ó���ϴ� �ڵ� ����� ��ġ
```python
try:
    # ������ ���� ��� �ڵ� ���
except:
    # ������ ������ �� ������ �ڵ�
```
* ex
```python
try:
    s1 = input()    
    s2 = input()
    print(int(s1) + int(s2))
except:
        print('���ڸ� �Է��ϼ���')
```
* ������ except���� ó��
```python
try:
    s1 = input()    
    s2 = input()
    print(int(s1) / int(s2))
except ValueError:
    print('���ڸ� �Է��ϼ���')
except ZeroDivisionError:
    print('0���� ���� �� �����ϴ�')
```
* �ݺ������� try ~ except ó��
```python
ar1 = [10, 20, 30]
ar2 = [5, 0]
for i in range(len(ar1)):
    try: 
        print(ar1[i] / ar2[i])
    except ZeroDivisionError:
        
        
        print('0���� ���� �� �����ϴ�.')
    except:
        print('������ �����Ͱ� �����մϴ�.')
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
* try���� ������ �����ϸ� ���� �� �ִ� else
```python
try:
    #
except:
    #
else:
    # except���� ������ �ʾ��� ��� �����ϴ� �ڵ� ���
```