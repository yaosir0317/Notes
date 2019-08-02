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
  const hobby = "basketball";
  var name = "liming";
  ```

- `const`定义的是非可变的"变量",从它被定义的那一刻开始,它的值就不能被改变(constant)

- `变量名`包含**$,_,字母,数字**但是不能以数字开头,切不能是js中的关键字

- `strict模式`

  ```
  //由于设计缺陷,name = 123同样可以定义变量,但是它带来的问题是name将变为全局变量,例如两个js文件都是用name作为变量,将会造成变量互相影响,
  解决的办法是在js文件的开头第一行代码写上:
  'use strict'
  ```

  

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
  // 循环数组 ES6
  for(let a of array){
  	console.log(a)
  }
  //
  for (var a in array) {
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

- forEach

  Set与Array类似，但Set没有索引，因此回调函数的前两个参数都是元素本身

  Map的回调函数参数依次为value、key和map本身

  ```
  var a = ['A', 'B', 'C'];
  a.forEach(function (element, index, array) {
  // element: 指向当前元素的值
  // index: 指向当前索引
  // array: 指向Array对象本身 console.log(element + ', index = ' + index);
  });
  
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

- 解构

  ```
  var [x, y, z] = ['hello', 'JavaScript', 'ES6'];
  ----
  // x, y, z分别被赋值为数组对应元素:
  console.log('x = ' + x + ', y = ' + y + ', z = ' + z);
  注意，对数组元素进行解构赋值时，多个变量要用[...]括起来。
  如果数组本身还有嵌套，也可以通过下面的形式进行解构赋值，注意嵌套层次和位置要保持一致:
  let [x, [y, z]] = ['hello', ['JavaScript', 'ES6']];
  解构赋值还可以忽略某些元素:
  let [, , z] = ['hello', 'JavaScript', 'ES6']; // 忽略前两个元素，只对z赋值第三个元素
  ```

  如果需要从一个对象中取出若干属性，也可以使用解构赋值，便于快速获取对象的指定属性:

  ```
  'use strict';
  var person = { 
      name: '小明',
      age: 20,
      gender: 'male',
      passport: 'G-12345678', 
      school: 'No.4 middle school'
  };
  var {name, age, passport} = person;
  ----
  // name, age, passport分别被赋值为对应属性:
  console.log('name = ' + name + ', age = ' + age + ', passport = ' + passport);
  // 把passport属性赋值给变量id:
  let {name, passport:id} = person;
  // 如果person对象没有single属性，默认赋值为true: 
  var {name, single=true} = person;
  ```

  有些时候，如果变量已经被声明了，再次赋值的时候，正确的写法也会报语法错误:

  ```
  // 声明变量:
  var x, y;
  // 解构赋值:
  {x, y} = { name: '小明', x: 100, y: 200};
  // 语法错误: Uncaught SyntaxError: Unexpected token =
  这是因为JavaScript引擎把{开头的语句当作了块处理，于是=不再合法。解决方法是用小括号括起来: 
  ({x, y} = { name: '小明', x: 100, y: 200});
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

- 额外位置形参`…` , ES6

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

- arguments

  arguments最常用于判断传入参数的个数

  ```
  function foo(a, b, c) {
    if (arguments.length === 2) {
     
    }
  }
  ```

- 关键字参数

## 变量提升

JavaScript的函数定义有个特点，它会先扫描整个函数体的语句，把所有申明的变量“提升”到函数顶部

```
'use strict';
function foo() {
    var x = 'Hello, ' + y; console.log(x);
    var y = 'Bob';
} 
foo();
```

虽然是strict模式，但语句var x = 'Hello, ' + y;并不报错，原因是变量y在稍后申明了。但是console.log显
示Hello, undefined，说明变量y的值为undefined。这正是因为JavaScript引擎自动提升了变量y的声明，但不会提升变量y的赋值。

对于上述foo()函数，JavaScript引擎看到的代码相当于:

```
function foo() {
  var y; // 提升变量y的申明，此时y为undefined 
  var x = 'Hello, ' + y;
  console.log(x);
  y = 'Bob';
}
```

由于JavaScript的这一怪异的“特性”，我们在函数内部定义变量时，请严格遵守“在函数内部首先申明所有变量”这一规则。最常见的做法是用一个var申明函数内部用到的所有变量:

```
function foo() { 
  	var
        x = 1, // x初始化为1
        y = x + 1, // y初始化为2 
        z, i; // z和i为undefined
    // 其他语句:
    for (i=0; i<100; i++) {
    			... 
    }
}

```

## 全局作用域

不在任何函数内定义的变量就具有全局作用域。实际上，JavaScript默认有一个全局对象window，全局作用域的变量实 际上被绑定到window的一个属性: 

```
'use strict';

var course = 'Learn JavaScript'; 
alert(course); // 'Learn JavaScript' 
alert(window.course); // 'Learn JavaScript'
```

因此，直接访问全局变量course和访问window.course是完全一样的。

## 名字空间

全局变量会绑定到window上，不同的JavaScript文件如果使用了相同的全局变量，或者定义了相同名字的顶层函数，都 会造成命名冲突，并且很难被发现。 

减少冲突的一个方法是把自己的所有变量和函数全部绑定到一个全局变量中。例如: 

```
// 唯一的全局变量MYAPP:
var MYAPP = {};
// 其他变量: 
MYAPP.name = 'myapp'; 
MYAPP.version = 1.0;
// 其他函数:
MYAPP.foo = function () {
		return 'foo'; 
};

```

## 局部作用域

由于JavaScript的变量作用域实际上是函数内部，我们在for循环等语句块中是无法定义具有局部作用域的变量的,为了解决块级作用域，ES6引入了新的关键字let，用let替代var可以申明一个块级作用域的变量;ES6标准还引入了新的关键字const来定义常量，const与let都具有块级作用域

## 装饰器

利用apply()，我们还可以动态改变函数的行为。JavaScript的所有对象都是动态的，即使内置的函数，我们也可以重新指向新的函数。现在假定我们想统计一下代码一共调用了多少次parseInt()，可以把所有的调用都找出来，然后手动加上count += 1，不过这样做太傻了。最佳方案是用我们自己的函数替换掉默认的parseInt(): 

```
'use strict';
var count = 0;
var oldParseInt = parseInt; // 保存原函数
window.parseInt = function () { 
      count += 1;
      return oldParseInt.apply(null, arguments); // 调用原函数 
};
```



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

var xiaoming = { 
    name: '小明', 
    birth: 1990,
    age: function () {
    		var y = new Date().getFullYear(); 
    		return y - this.birth;
    } 
};

```

绑定到对象上的函数称为方法，和普通函数也没啥区别，但是它在内部使用了一个this关键字,在一个方法内部，this是一个特殊变量，它始终指向当前对象，也就是xiaoming这个变量。所以，this.birth可以拿 到xiaoming的birth属性。 

```
function getAge() {
		var y = new Date().getFullYear(); 
		return y - this.birth;
}
var xiaoming = { 
    name: '小明', 
    birth: 1990,
    age: getAge 
};
xiaoming.age(); // 25, 正常结果 
getAge(); // NaN
------------------------------------------
单独调用函数getAge()怎么返回了NaN?请注意，我们已经进入到了JavaScript的一个大坑里。
JavaScript的函数内部如果调用了this，那么这个this到底指向谁?
答案是，视情况而定!
如果以对象的方法形式调用，比如xiaoming.age()，该函数的this指向被调用的对象，也就是xiaoming，这是符合我们预期的。
如果单独调用函数，比如getAge()，此时，该函数的this指向全局对象，也就是window。
```

由于这是一个巨大的设计错误，要想纠正可没那么简单。ECMA决定，在strict模式下让函数的this指向undefined，因此，在strict模式下，你会得到一个错误

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

- 定义

  ```
  let array = []  // js数组可以包含任意数据类型，并通过索引来访问每个元素。
  ```

- 属性

  ```
  array.length = 5 // 当赋值给数组的长度时,会改变数组的大小 
  array[6] = 5 // 通过索引赋值时,索引超过范围,同样会引起array大小的变化
  ```

- 方法

  ```
  array.push(1)		// 末尾添加
  array.pop()			// 末尾删除
  array.unshift()	// 开头添加
  array.shift(2)	// 开头删除
  array.indexOf(element)  //返回元素的index
  array.slice(2,4)  // 切片,互相独立
  array.concat([0]) //列表合并为新列表
  array.sort()  // 排序
  array.reverse()  // 反转
  array.splice 
  // 数组修改的万能方法
  var arr = ['Microsoft', 'Apple', 'Yahoo', 'AOL', 'Excite', 'Oracle'];
  // 从索引2开始删除3个元素,然后再添加两个元素:
  arr.splice(2, 3, 'Google', 'Facebook'); // 返回删除的元素 ['Yahoo', 'AOL', 'Excite'] 
  arr; // ['Microsoft', 'Apple', 'Google', 'Facebook', 'Oracle']
  // 只删除,不添加:
  arr.splice(2, 2); // ['Google', 'Facebook']
  arr; // ['Microsoft', 'Apple', 'Oracle']
  // 只添加,不删除:
  arr.splice(2, 0, 'Google', 'Facebook'); // 返回[],因为没有删除任何元素 arr; // ['Microsoft', 'Apple', 'Google', 'Facebook', 'Oracle']
  ```

- map/reduce/filter

  ```
  var arr = [1, 2, 3, 4, 5, 6, 7, 8, 9];
  arr.map(String); // ['1', '2', '3', '4', '5', '6', '7', '8', '9']
  ```

  Array的reduce()把一个函数作用在这个Array的[x1, x2, x3...]上，这个函数必须接收两个参数，reduce()把结果继续和序列的下一个元素做累积计算

  ```
  var arr = [1, 3, 5, 7, 9];  // 求和
  arr.reduce(function (x, y) {
  		return x + y; 
  }); // 25
  
  ```

  filter也是一个常用的操作，它用于把Array的某些元素过滤掉，然后返回剩下的元素

  ```
  var arr = [1, 2, 4, 5, 6, 9, 10, 15]; 
  var r = arr.filter(function (x) {
  		return x % 2 !== 0; 
  });
  r; // [1, 5, 9, 15] 保留奇数
  // 接收多个参数
  var arr = ['A', 'B', 'C'];
  var r = arr.filter(function (element, index, self) {
    console.log(element); // 依次打印'A', 'B', 'C' 
    console.log(index); // 依次打印0, 1, 2 
    console.log(self); // self就是变量arr
    return true;
  });
  ```

  

## 字符串

- 多行字符串

  ```
  a = `这是一个 
  		 多行
       字符串`;
  ```

- 模板字符串

  ```
  var name = 'yao';
  var age = 20;
  console.log(`你好, ${name}, 你今年${age}岁了!`);
  ```

- 方法

  ```
  string.slice(4, 7)
  string.indexOf("u")  // 搜索字符出现的位置,区别array的是可以取多字符的索引
  string.trim()  // 去空白
  String(6).padStart(3, "0") // 实现高位补充字符,此处是返回一个新字符串
  string.split(" ")  // 以空格切割
  array.join(",")   // 以逗号拼接
  string.repeat(n)  // 重复拼接字符串n次,形成一个新字符串
  string.toUpperCase // 大写
  string.toLowerCase // 小写
  ```

## Map & Set

- map

  Map是一组键值对的结构，具有极快的查找速度。初始化Map需要一个二维数组，或者初始化一个空Map

  ```
  var m = new Map([['Michael', 95], ['Bob', 75], ['Tracy', 85]]);
  var m = new Map(); // 空Map 
  m.set('Adam', 67); // 添加新的key-value 
  m.set('Bob', 59);
  m.has('Adam'); //  是否存在key 'Adam': true 
  m.get('Adam'); //  67
  m.delete('Adam'); // 删除key 'Adam' undefined
  m.get('Adam'); //
  ```

- Set

  Set和Map类似，也是一组key的集合，但不存储value。由于key不能重复，所以，在Set中，没有重复的key。要创建一个Set，需要提供一个Array作为输入，或者直接创建一个空Set

  ```
  var s1 = new Set(); // 空Set
  var s2 = new Set([1, 2, 3]); // 含1, 2, 3
  s1.add(4);
  s1.delete(3);
  ```

# 对象

## Math

```
Math.random()  // 返回0-1之间的随机数
Math.PI  
Math.floor(Math.random() * 10)  // js实现随机数
```

