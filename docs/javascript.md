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

- **类型转换**,当运算时遇到错误类型的值时,js会自动转换为它所需要的类型

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
  // 循环数组
  for(let a of array){
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

## 定义

```
// 1  
function fn(x){
	return x*x  // 未定义return值则返回undefined
}
//2 let/var同理
const fn=function(x){
	return x*x
}
```

## 使用

- 函数声明不是常规的从上到下控制流程的一部分,你永远不用担心因使用函数在定义函数之前而报错

- ```
  // 不会报错
  console.log("The future says:", future());
  function future() {
  	return "You'll never have flying cars";
  }
  ```

- 闭包

  ```
  function wrapValue(n) {
    let local = n;
    return () => local;
  }
  let wrap1 = wrapValue(1);
  let wrap2 = wrapValue(2);
  console.log(wrap1());
   // → 1
  console.log(wrap2());
  // → 2
  
  
  //另一种更简单的表示形式
  function multiplier(factor) {
     return number => number * factor;
  }
  let twice = multiplier(2);
  console.log(twice(5));
   // → 10
  
  ```

- 递归

  在典型的js实现中,递归相较于循环慢了大约三倍

  ```
  function power(exponent) {
     if (exponent == 1) {
       return 1;
     } else {
       return exponent*power(exponent-1);
     }
  }
  console.log(power(6));
   // → 720 实现n的阶乘
  ```

  

## 箭头函数

```
// 箭头函数多参数形式
const power = (base, exponent) => {
   let result = 1;
   for (let count = 0; count < exponent; count++) {
     result *= base;
   }
   return result;
 };
 // 箭头函数单参数形式
const square1 = (x) => { return x * x; };
const square2 = x => x * x;
 // 箭头函数无参数形式
const horn = () => { console.log("Toot");
};
```

## 参数

- 位置参数

  js中函数使用位置参数会将少传的参数默认使用undefined替代,而额外多传的参数将会被忽略

  ```
  function minus(a, b) {
     if (b === undefined) return -a;
     else return a - b;
  }
  console.log(minus(10));
  // → -10
  console.log(minus(10, 5));
  // → 5
  console.log(minus(10, 5, "hello world"));
  // → 5
  ```

- 额外位置形参`...`

  ```
  function max(...numbers) {
     let result = -Infinity;
     for (let number of numbers) {
       if (number > result) result = number;
     }
     return result;
   }
   console.log(max(4, 1, 9, -2));
  ```

  

- 关键字参数



# 数据结构

## 属性

所有的js对象都有属性,除了null和undefined

```
let a = [1, 2, 3]
console.log(a.length)  // → 3
console.log(null.length)  // → TypeError: Cannot read property
```

属性的使用通过两种方式`.`和`[]`,但是这俩种方式不一定表示的是同一种属性

```
let a = [1, 2, 3]
console.log(a.length)  // → 3
console.log(a["length"])  // → 3
```

## 方法

通过`.methodName()`使用

```
let doh = "Doh";
console.log(typeof doh.toUpperCase); // → function 
console.log(doh.toUpperCase());  // → DOH
```

## 对象

```
let day1 = {
	squirrel: false,
	events: ["work", "touched tree", "pizza", "running"]
}; 
console.log(day1.squirrel); // → false 
console.log(day1.wolf);  // → undefined
day1.wolf = false; 
console.log(day1.wolf);  // → false
```

删除对象属性,判断属性存在

```
let anObject = {left: 1, right: 2};
console.log(anObject.left);
 // → 1
delete anObject.left;
console.log(anObject.left);
// → undefined
console.log("left" in anObject); // → false
console.log("right" in anObject); // → true
```

查看对象所有属性

```
let al = {a: 1, b: 2};
console.log(Object.keys(al));
```

将对象的属性拷贝到另一个对象

```
let objectA = {a: 1, b: 2}; 
Object.assign(objectA, {b: 3, c: 4}); 
console.log(objectA);// → {a: 1, b: 3, c: 4}
```

使用`const`建立的对象

```
const score = {visitors: 0, home: 0}; 
// This is okay
score.visitors = 1;
// This isn't allowed
score = {visitors: 1, home: 1};
```

## 数组

定义

```
let array = []
```

方法

```
array.push(1)		// 末尾添加
array.pop()			// 末尾删除
array.unshift()	// 开头添加
array.shift(2)	// 开头删除
array.indexOf(element)  //返回元素的index
array.slice(2,4)  // 切片,互相独立
array.concat([0]) //列表合并为新列表
```

## 字符串

方法

```
string.slice(4, 7)
string.indexOf("u")  // 区别array的是可以取多字符的索引
string.trim()  // 去空白
String(6).padStart(3, "0") // 实现高位补充字符,此处是返回一个新字符串
string.split(" ")  // 以空格切割
array.join(",")   // 以逗号拼接
string.repeat(n)  // 重复拼接字符串n次,形成一个新字符串
```



# 对象

## Math

```
Math.random()  // 返回0-1之间的随机数
Math.PI  
Math.floor(Math.random() * 10)  // js实现随机数
```

