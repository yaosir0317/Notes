# python小知识

1. 控制台的最后一次输出会赋值给 `_`

   ```
   >>>6*5
   30
   >>>_
   30
   ```

2. 相邻的字符串会被自动拼接

   ```
   >>>"py"     "thon"
   'python'
   ```

3. 字符串可以从右边开始切片,右边的第一个索引为`-1`,因为0和0相等

4. `-3**2`被认为是 ` -(3**2)`

5. 函数使用变量作为其默认值时,函数执行时会使用它定义那一时刻,变量的值作为默认值

   ```
   i = 5
   def f(arg=i):
       print(arg)
   i = 6
   f()
   will print 5
   ```

6. 通过列表可以很容易的形成栈

   ```
   append()
   pop()
   ```

7. 通过列表也可以形成队列

   ```
   from collections import deque
   queue = deque(["Eric", "John", "Michael"])
   queue.append("Terry")           # Terry arrives
   queue.popleft()                 # The first to arrive now leaves 
   ```

8. python中的圆周率`π`

   ```
   from math import pi
   ```

9. 一个元素不带括号也是元组

   ```
   t = 12345,   
   type(t) = <class 'tuple'>
   ```

10. 可以将字典通过类型转换为列表,结果是字典的键,还可以通过`sorted`排序

    ```
    dic = {1: "a", 3: "b", 2: "c"}
    >>>list(dic)
    [1, 3, 2]
    >>>sorted(dic)
    [1, 2, 3]
    ```

11. 使用`zip`可以同时循环多个序列

    ```
    questions = ['name', 'favorite color']
    answers = ['lancelot', 'blue']
    for q, a in zip(questions, answers):
        print(f'What is your {q}?  {a}.')
    -------------------------------------
    What is your name?  lancelot.
    What is your favorite color?  blue.
    ```

12. `and`和`or`判断时当左边满足判断条件就不会继续判断右边

    ```
    a = 0
    b = False
    print(a or b)  # False
    print(a and b)  # 0
    
    c = 1
    d = True
    print(c or d)  # 1
    print(c and d)  # True
    ```

13. 通过`dir`查看模块

    ```
    >>>dir(requests)
    ['ConnectTimeout', 'ConnectionError', 'DependencyWarning', 'FileModeWarning', 'HTTPError', 'NullHandler', 'PreparedRequest', 'ReadTimeout', 'Request', 'RequestException', 'RequestsDependencyWarning', 'Response', 'Session', 'Timeout', 'TooManyRedirects', 'URLRequired', '__author__', '__author_email__', '__build__', '__builtins__', '__cached__', '__cake__', '__copyright__', '__description__', '__doc__', '__file__', '__license__', '__loader__', '__name__', '__package__', '__path__', '__spec__', '__title__', '__url__', '__version__', '_check_cryptography', '_internal_utils', 'adapters', 'api', 'auth', 'certs', 'chardet', 'check_compatibility', 'codes', 'compat', 'cookies', 'delete', 'exceptions', 'get', 'head', 'hooks', 'logging', 'models', 'options', 'packages', 'patch', 'post', 'put', 'request', 'session', 'sessions', 'status_codes', 'structures', 'urllib3', 'utils', 'warnings']
    ```

14. `repr`原样输出

    ```
    >>>print(repr("hello world\n"))
    'hello world\n'
    ```

15. `replace`还可以替换时间格式

    ```
    date.replace(day=12)
    ```

16. 移位运算

    ```
    num = 8
    num >>= 1  # 右移一位 1000 -> 0100,结果为4
    num <<= 1  # 左移一位 1000 -> 10000, 结果为16
    ```

    