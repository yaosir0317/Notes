# 值,类型和操作

## 特殊值

- `Infinity`表示无穷大,无穷小用`-Infinity`表示

- `NaN`表示虽然是数字类型,但并不是数字,例如`0/0`和`Infinity-Infinity`等

  ```
  console.log(NaN == NaN)  // NaN是js中唯一一个与自身不相等的值
  ```

- `undefined`和`null`表示它们自己值,但是这个值没有携带信息

## 字符串

- 被`反引号包起来的${}`中的数值会被计算,然后转换成字符串

  ```
  console.log(`half of 100 is ${5*10}`)
  ```

- 字符串比较时,大写字母要小于小写字母

  ```
  console.log("Aardvark" < "oroaster")
  ```

  

## 操作

- 三元运算

  ```
  console.log(true ? 1 : 2);  //true取值:左边
  console.log(false ? 1 : 2);  //false取值:右边
  ```

- 类型转换,当运算时遇到错误类型的值时,js会自动转换为它所需要的类型

  ```
  console.log(8 * null) // null 被认为 0
  console.log("5" - 1)  // "5" 被认为 5
  console.log("five" * 2)  // "five" 被认为 NaN
  
  ```

- 类型比较

  ```
  // ==可以用来判断俩边类型是否相同
  console.log(null == undefined); // → true
  console.log(null == 0);  // → false
  // 如果你只想判断俩边值是否相等时,可以使用===
  console.log("2" == 2);  // → true
  ```

- 逻辑判断,当使用逻辑运算`&&`和`||`时,但满足左边条件时,将不会执行右边,即使右边是未定义的值

  ```
  console.log(true || X)  // X未定义,但不会报错,输出为true
  ```

  

# 程序结构

## 变量

- 定义变量

  ```
  let a = 1;
  let a = 1, b = 2;
  var name = "liming"
  const hobby = "basketball"
  ```

- `const`定义的是非可变的"变量",从它被定义的那一刻开始,它的值就不能被改变(constant)

- `变量名`包含**$,_,字母,数字**但是不能以数字开头,切不能是js中的关键字

## 条件和循环

- if-else

  ```
  let x = 2;
  if(x<0){
  	console.log(1);
  }elif(x>10){
  	console.log(2);
  }else{
  	console.log(3);
  }
  ```

- `while`

  ```
  let n = 10;
  while(n>0){
  	n = n - 1;
  	console.log(n)
  }
  ```

- `do-while`

  ```
  do{
  	console.log(1);
  }while(true)
  ```

- `for`

  ```
  for(let a=10;a>0;a--){
  	console.log(a)
  }
  ```

- `switch`

  ```
  function fn(n){
  	return n/2
  }
  switch(fn(2)){
  	case 0:
  		console.log("n=0");
  	case 1:
  		console.log("n=2");
  	default:
  		console.log("other");
  }
  ```

  

## 捷径

```
let result = 1;
result = result + 1 等价于 result += 1  等价于 result++  //其余运算同理
```



# 函数

# 数据结构

# 对象