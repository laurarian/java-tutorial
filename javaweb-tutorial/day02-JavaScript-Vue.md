# 1 JavaScript

html完成了架子，css做了美化，但是网页是死的，我们需要给他注入灵魂，所以接下来我们需要学习JavaScript，这门语言会让我们的页面能够和用户进行交互。
通过**代码/js效果演示**提供资料进行效果演示，通过浏览器打开，我们点击主题5按钮，页面的主题发生了变化，所以js可以让我们的页面更加的智能，让页面和用户进行交互。

## 1.1 引入方式
同样，js代码也是书写在html中的，那么html中如何引入js代码呢？主要通过下面的2种引入方式：

**第一种方式：** 内部脚本，将JS代码定义在HTML页面中

- JavaScript代码必须位于&lt;script&gt;&lt;/script&gt;标签之间
- 在HTML文档中，可以在任意地方，放置任意数量的&lt;script&gt;
- 一般会把脚本置于&lt;body&gt;元素的底部，可改善显示速度

例子：

~~~html
<script>
    alert("Hello JavaScript")
</script>
~~~



**第二种方式：** 外部脚本将， JS代码定义在外部 JS文件中，然后引入到 HTML页面中

- 外部JS文件中，只包含JS代码，不包含&ltscript&gt;标签
- 引入外部js的&lt;script&gt;标签，必须是双标签

例子：

~~~html
<script src="js/demo.js"></script>
~~~

注意：demo.js中只有js代码，没有&lt;script&gt;标签

## 1.2 基础语法
### 1.2.1 书写语法
语法规则如下：

- 区分大小写：与 Java 一样，变量名、函数名以及其他一切东西都是区分大小写的

- 每行结尾的分号可有可无,建议写上更严谨。

- 大括号表示代码块

- 注释：

  - 单行注释：// 注释内容

  - 多行注释：/* 注释内容 */


我们需要借助js中3种输出语句，来演示书写语法

| api              | 描述             |
| ---------------- | ---------------- |
| window.alert()   | 警告框           |
| document.write() | 在HTML 输出内容  |
| console.log()    | 写入浏览器控制台 |

<img width="833" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/abd50e56-f4ae-4402-a344-c314a3867d7d">


~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JS-基本语法</title>
</head>
<body>
    
</body>
<script>
    /* alert("JS"); */

    //方式一: 弹出警告框
    window.alert("hello js");

    // 方式二: 写入html页面中
    document.write("hello js");

    //方式三: 控制台输出
    console.log("hello js");
</script>
</html>
~~~

### 1.2.2 变量
js主要通过如下3个关键字来声明变量的：

| 关键字 | 解释                                                         |
| ------ | ------------------------------------------------------------ |
| var    | 早期ECMAScript5中用于变量声明的关键字                        |
| let    | ECMAScript6中新增的用于变量声明的关键字，相比较var，let只在代码块内生效 |
| const  | 声明常量的，常量一旦声明，不能修改                           |

在js中声明变量还需要注意如下几点：

- JavaScript 是一门弱类型语言，变量可以存放不同类型的值 。
- 变量名需要遵循如下规则：
  - 组成字符可以是任何字母、数字、下划线（_）或美元符号（$）
  - 数字不能开头
  - 建议使用驼峰命名

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JS-基础语法</title>
</head>
<body>
    
</body>
<script>

    // //1. var定义变量
    // var a = 10;
    // a = "张三";
    // alert(a);

    // // 特点1： 作用域比较大，全局变量
    // // 特点2： 可以重复定义的
    // {
    //     var x = 1;
    //     var x = "A" // java中会报错，不能重复声明
    // }

    // 2. let: 局部变量；不能重读定义
    {
        let x = 1;
        alert(x);
    
    }
    // 3. const： 常量，不能改变的
    
</script>
</html>
~~~

注意事项：
1. ECMAScript 6 新增了 **let**关键字来定义变量，它的用法类似于 var，但是所声明的变量，只在 let关键字所在的代码块内有效，且不允许重复声明。
2. ECMAScript6中，还新增了const关键字用来声明常量，但是一旦声明，常量的值是无法更改的。


### 1.3.3 数据类型和运算符

虽然js是弱数据类型的语言，但是js中也存在数据类型，js中的数据类型分为 ：原始类型 和 引用类型，具体有如下类型

| 数据类型  | 描述                                               |
| --------- | -------------------------------------------------- |
| number    | 数字（整数、小数、NaN(Not a Number)）              |
| string    | 字符串，单双引皆可                                 |
| boolean   | 布尔。true，false                                  |
| null      | 对象为空                                           |
| undefined | 当声明的变量未初始化时，该变量的默认值是 undefined |

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JS-数据类型</title>
</head>
<body>

</body>
<script>

    //原始数据类型
    alert(typeof 3); //number
    alert(typeof 3.14); //number

    alert(typeof "A"); //string
    alert(typeof 'Hello'); //string

    alert(typeof true); //boolean
    alert(typeof false); //boolean

    alert(typeof null); //object

    var a ;
    alert(typeof a); //undefined
        
</script>
</html>
~~~
<img width="440" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/1803da24-22bd-486e-8323-fdee4510fc10">


js中的运算规则绝大多数还是和java中一致的，具体运算符如下：

| 运算规则   | 运算符                                                       |
| ---------- | ------------------------------------------------------------ |
| 算术运算符 | + , - , * , / , % , ++ , --                                  |
| 赋值运算符 | = , += , -= , *= , /= , %=                                   |
| 比较运算符 | &gt; , < , >= , <= , != , == , ===   注意     == 会进行类型转换，=== 不会进行类型转换 |
| 逻辑运算符 | && , \|\| , !                                                |
| 三元运算符 | 条件表达式 ? true_value: false_value                         |

在js中，绝大多数的运算规则和java中是保持一致的，但是js中的\==和===是有区别的。

- \==：只比较值是否相等，不区分数据类型，哪怕类型不一致，==也会自动转换类型进行值得比较
- ===：不光比较值，还要比较类型，如果类型不一致，直接返回false

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JS-运算符</title>
</head>
<body>
    
</body>
<script>
     var age = 20;
     var _age = "20";
     var $age = 20;
    
     alert(age == _age);//true ，只比较值
     alert(age === _age);//false ，类型不一样
     alert(age === $age);//true ，类型一样，值一样

</script>
</html>
~~~

<img width="341" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/2450a925-eac9-46d8-9e10-b15cbd35a4b3">

js中可以通过parseInt()函数来进行将其他类型转换成数值类型

<img width="683" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/5bf89ddb-f8ed-4a8f-9700-31a954cad58f">

~~~js
// 类型转换 - 其他类型转为数字
alert(parseInt("12")); //12
alert(parseInt("12A45")); //12
alert(parseInt("A45"));//NaN (not a number)
~~~

其他情况可以一一演示，完整演示代码如下：

~~~js
    // if(0){ //false
    //     alert("0 转换为false");
    // }
    // if(NaN){//false
    //     alert("NaN 转换为false");
    // }
    if(1){ //true
        alert("除0和NaN其他数字都转为 true");
    }

    // if(""){ //false
    //     alert("空字符串为 false, 其他都是true");
    // }
        
    // if(null){ //false
    //     alert("null 转化为false");
    // }
    // if(undefined){ //false
    //     alert("undefined 转化为false");
    // }
~~~

流程控制语句和Java语法一致

<img width="653" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/aec685cf-cf92-4b68-b033-685ffd7a5d4b">

## 1.3 函数
### 第一种定义格式

第一种定义格式如下：

~~~js
function 函数名(参数1,参数2..){
    要执行的代码
}
~~~

因为JavaScript是弱数据类型的语言，所以有如下几点需要注意：

- 形式参数不需要声明类型，并且JavaScript中不管什么类型都是let或者var去声明，加上也没有意义。
- 返回值也不需要声明类型，直接return即可

如下示例：

~~~js
function add(a, b){
    return a + b;
}
~~~

### 第二种定义格式
第二种可以通过var去定义函数的名字，具体格式如下：

~~~js
var functionName = function (参数1,参数2..){   
	//要执行的代码
}
~~~

例子：
~~~html
<script>

    //定义函数-1
    // function add(a,b){
    //    return  a + b;
    // }

    //定义函数-2
    var add = function(a,b){
        return  a + b;
    }


    //函数调用
    var result = add(10,20);
    alert(result);
    
</script>
~~~
注意：
1. JS中，函数参数调用可以传递任意个数的参数。

## 1.4 JavaScript对象

<img width="428" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/bb5ae928-7db6-4cbb-b774-b33fe43d2865">

### 1.4.1 基本对象
#### 1.4.1.1 Array对象
**语法:**
<img width="684" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/919fb1c5-2f63-4609-a4ab-155e9dcaa2fb">

与java中不一样的是，JavaScript中数组相当于java中的集合，数组的长度是可以变化的。而且JavaScript是弱数据类型的语言，所以数组中可以存储任意数据类型的值。
~~~js
//特点: 长度可变 类型可变
var arr = [1,2,3,4];
arr[10] = 50;

// console.log(arr[10]);
// console.log(arr[9]);
// console.log(arr[8]);

arr[9] = "A";
arr[8] = true;

console.log(arr);
~~~

**属性和方法:**
Array作为一个对象，那么对象是有属性和方法的，所以接下来我们介绍一下Array对象的属性和方法

官方文档中提供了Array的很多属性和方法，但是我们只学习常用的属性和方法，如下图所示：

**属性：**

| 属性   | 描述                         |
| :----- | :--------------------------- |
| length | 设置或返回数组中元素的数量。 |

**方法：**

| 方法方法  | 描述                                             |
| :-------- | :----------------------------------------------- |
| forEach() | 遍历数组中的每个有值得元素，并调用一次传入的函数 |
| push()    | 将新元素添加到数组的末尾，并返回新的长度         |
| splice()  | 从数组中删除元素                                 |

- length属性：

  length属性可以用来获取数组的长度，所以我们可以借助这个属性，来遍历数组中的元素，添加如下代码：

  ~~~js
  var arr = [1,2,3,4];
  arr[10] = 50;
  	for (let i = 0; i < arr.length; i++) {
  	console.log(arr[i]);
  }
  ~~~

  浏览器控制台输出结果如图所示：

  <img width="826" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/16c91cac-89e6-4045-aca1-176facd7a864">






- forEach()函数

  首先我们学习forEach()方法，顾名思义，这是用来遍历的，那么遍历做什么事呢？所以这个方法的参数，需要传递一个函数，而且这个函数接受一个参数，就是遍历时数组的值。修改之前的遍历代码如下：

  ~~~js
  //e是形参，接受的是数组遍历时的值
  arr.forEach(function(e){
       console.log(e);
  })
  ~~~

  当然了，在ES6中，引入箭头函数的写法，语法类似java中lambda表达式，修改上述代码如下：

  ~~~js
  arr.forEach((e) => {
       console.log(e);
  }) 
  ~~~



  浏览器输出结果如下：注意的是，没有元素的内容是不会输出的，因为forEach只会遍历有值的元素 

  <img width="865" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/6ab5fc87-c244-4dca-bce7-2451829c5a58">




- push()函数

  push()函数是用于向数组的末尾添加元素的，其中函数的参数就是需要添加的元素，编写如下代码：向数组的末尾添加3个元素

  ~~~js
  //push: 添加元素到数组末尾
  arr.push(7,8,9);
  console.log(arr);
  ~~~

  浏览器输出结果如下：

  <img width="835" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/e0938c05-d9c8-4988-b655-90860abda356">


  



- splice()函数

  splice()函数用来数组中的元素，函数中填入2个参数。

  参数1：表示从哪个索引位置删除

  参数2：表示删除元素的个数

  如下代码表示：从索引2的位置开始删，删除2个元素

  ~~~js
  //splice: 删除元素
  arr.splice(2,2);
  console.log(arr);
  ~~~

  浏览器执行效果如下：元素3和4被删除了，元素3是索引2

 <img width="833" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/9bf36bba-2e9a-46ae-a6b7-d28a474a6d28">




Array数组的完整代码如下：

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JS-对象-Array</title>
</head>
<body>
    
</body>
<script>
    //定义数组
    // var arr = new Array(1,2,3,4);
    // var arr = [1,2,3,4];

    // console.log(arr[0]);
    // console.log(arr[1]);

    //特点: 长度可变 类型可变
    // var arr = [1,2,3,4];
    // arr[10] = 50;

    // console.log(arr[10]);
    // console.log(arr[9]);
    // console.log(arr[8]);

    // arr[9] = "A";
    // arr[8] = true;

    // console.log(arr);



    var arr = [1,2,3,4];
    arr[10] = 50;
    // for (let i = 0; i < arr.length; i++) {
    //     console.log(arr[i]);
    // }

    // console.log("==================");

    //forEach: 遍历数组中有值的元素
    // arr.forEach(function(e){
    //     console.log(e);
    // })

    // //ES6 箭头函数: (...) => {...} -- 简化函数定义.类似java中lamda表达式
    // arr.forEach((e) => {
    //     console.log(e);
    // }) 

    //push: 添加元素到数组末尾
    // arr.push(7,8,9);
    // console.log(arr);

    //splice: 删除元素
    arr.splice(2,2);
    console.log(arr);

</script>
</html>
~~~


#### 1.4.1.2 String对象

<img width="692" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/9d499cbc-ecb2-43d8-b59d-c83e7a6444e9">

- length属性：

  length属性可以用于返回字符串的长度，添加如下代码：

  ~~~js
  //length
  console.log(str.length);
  ~~~

- charAt()函数：

  charAt()函数用于返回在指定索引位置的字符，函数的参数就是索引。添加如下代码：

  ~~~js
  console.log(str.charAt(4));
  ~~~

- indexOf()函数

  indexOf()函数用于检索指定内容在字符串中的索引位置的，返回值是索引，参数是指定的内容。添加如下代码：

  ~~~js
  console.log(str.indexOf("lo"));
  ~~~

- trim()函数

  trim()函数用于去除字符串两边的空格的。添加如下代码：

  ~~~js
  var s = str.trim();
  console.log(s.length);
  ~~~

- substring()函数

  substring()函数用于截取字符串的，函数有2个参数。

  参数1：表示从那个索引位置开始截取。包含

  参数2：表示到那个索引位置结束。不包含

  ~~~js
  console.log(s.substring(0,5));
  ~~~

注意：
1.你可以使用单引号 (') 或双引号 (") 来定义字符串。这两种方式在 JavaScript 中是互换的.
2. 在使用字符串时，如果字符串内部需要包含引号，通常选择外部使用不同类型的引号或者使用相同类型的引号但要进行转义。
<img width="553" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/19815385-c4f0-42df-b925-ac030225c65d">



整体代码如下：

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JS-对象-String</title>
</head>
<body>
    
</body>
<script>
    //创建字符串对象
    //var str = new String("Hello String");
    var str = "  Hello String    ";

    console.log(str);

    //length
    console.log(str.length);

    //charAt
    console.log(str.charAt(4));

    //indexOf
    console.log(str.indexOf("lo"));

    //trim
    var s = str.trim();
    console.log(s.length);

    //substring(start,end) --- 开始索引, 结束索引 (含头不含尾)
    console.log(s.substring(0,5));

</script>
</html>
~~~



浏览器执行效果如图所示：
<img width="852" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/5c0fb97e-261e-427c-b422-75671927d7d3">


#### 1.4.1.3 JSON对象

**JAVA自定义对象**

<img width="739" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/46bc14a6-b447-40ba-b544-95f8dca509cc">


~~~html
<script>
    //自定义对象
    var user = {
        name: "Tom",
        age: 10,
        gender: "male",
        eat: function(){
             console.log("用膳~");
         }
    }

    console.log(user.name);
    user.eat();
<script>
~~~
其中上述函数定义的语法可以简化成如下格式：
~~~js
    var user = {
        name: "Tom",
        age: 10,
        gender: "male",
        // eat: function(){
        //      console.log("用膳~");
        //  }
        eat(){
            console.log("用膳~");
        }
    }
~~~

**json对象 - 介绍**

<img width="670" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/eb7207e9-5159-4595-963e-212b03914422">

注意：
1. 其中，**key必须使用引号并且是双引号标记，value可以是任意数据类型。**

例如我们可以直接百度搜索“json在线解析”，随便挑一个进入，然后编写内容如下：

~~~js
{
	"name": "李传播"
}
~~~

但是当我们将双引号切换成单引号，再次校验，则报错。
2. Jason的用途 - 用来作为前后台交互的数据载体
   如下图所示：前后台交互时，我们需要传输数据，但是java中的对象我们该怎么去描述呢？我们可以使用如图所示的xml格式，可以清晰的描述java中需要传递给前端的java对象。

<img width="780" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/b04fbab2-94da-44a6-9979-fd6895a94252">

但是xml格式存在如下问题：

- 标签需要编写双份，占用带宽，浪费资源
- 解析繁琐

所以我们可以使用json来替代，如下图所示：
<img width="793" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/a9ba17b7-01a6-45c0-a33d-070404e35bc5">



**json对象 - 语法**


<img width="698" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/ed66f800-f794-4a08-919a-49885687fb68">


~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JS-对象-JSON</title>
</head>
<body>
    
</body>
<script>
    //自定义对象
    // var user = {
    //     name: "Tom",
    //     age: 10,
    //     gender: "male",
    //     // eat: function(){
    //     //      console.log("用膳~");
    //     //  }
    //     eat(){
    //         console.log("用膳~");
    //     }
    // }

    // console.log(user.name);
    // user.eat();


    // //定义json
    var jsonstr = '{"name":"Tom", "age":18, "addr":["北京","上海","西安"]}';
    //alert(jsonstr.name);

    // //json字符串--js对象
    var obj = JSON.parse(jsonstr);
    //alert(obj.name);

    // //js对象--json字符串
    alert(JSON.stringify(obj));


</script>
</html>
~~~

注意：
1.在 JavaScript 中，使用单引号或双引号来定义字符串都是有效的，关键是要保持一致性。
<img width="575" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/202e6aac-b3e9-4a5f-b30a-728dd305dedb">


### 1.4.2 BOM对象(Browser Object Model 浏览器对象模型)
### 1.4.3 DOM对象(Document Object Model 文档对象模型)

**介绍**
DOM：Document Object Model 文档对象模型。也就是 JavaScript 将 HTML 文档的各个组成部分封装为对象。

DOM 其实我们并不陌生，之前在学习 XML 就接触过，只不过 XML 文档中的标签需要我们写代码解析，而 HTML 文档是浏览器解析。封装的对象分为

- Document：整个文档对象
- Element：元素对象
- Attribute：属性对象
- Text：文本对象
- Comment：注释对象

如下图，左边是 HTML 文档内容，右边是 DOM 树

<img width="892" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/b74b3458-4868-44c0-9721-424a716d3079">


JavaScript通过DOM,就能对HTML进行操作：：

- 改变 HTML 元素的内容
- 改变 HTML 元素的样式（CSS）
- 对 HTML DOM 事件作出反应
- 添加和删除 HTML 元素

总而达到动态改变页面效果目的，具体我们可以查看代码中提供的06. JS-对象-DOM-演示.html来体会DOM的效果。

<img width="784" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/cdab304c-fcb4-46cb-8ea8-39ed41d05862">

**获取DOM对象**
我们知道DOM的作用是通过修改HTML元素的内容和样式等来实现页面的各种动态效果，但是我们要操作DOM对象的前提是先获取元素对象，然后才能操作。所以学习DOM,主要的核心就是学习如下2点：

- 如何获取DOM中的元素对象（Element对象 ，也就是标签）
- 如何操作Element对象的属性,也就是标签的属性。

接下来我们先来学习如何获取DOM中的元素对象。

HTML中的Element对象可以通过Document对象获取，而Document对象是通过window对象获取的。document对象提供的用于获取Element元素对象的api如下表所示：

| 函数                              | 描述                                     |
| --------------------------------- | ---------------------------------------- |
| document.getElementById()         | 根据id属性值获取，返回单个Element对象    |
| document.getElementsByTagName()   | 根据标签名称获取，返回Element对象数组    |
| document.getElementsByName()      | 根据name属性值获取，返回Element对象数组  |
| document.getElementsByClassName() | 根据class属性值获取，返回Element对象数组 |

接下来我们通过VS Code中创建名为12. JS-对象-DOM-获取元素.html的文件来演示上述api

接下来我们通过VS Code中创建名为07. JS-对象-DOM-获取元素.html的文件来演示上述api，首先在准备如下页面代码：

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JS-对象-DOM</title>
</head>

<body>
    <img id="h1" src="img/off.gif">  <br><br>

    <div class="cls">传智教育</div>   <br>
    <div class="cls">黑马程序员</div>  <br>

    <input type="checkbox" name="hobby"> 电影
    <input type="checkbox" name="hobby"> 旅游
    <input type="checkbox" name="hobby"> 游戏
</body>

</html>
~~~

- document.getElementById()： 根据标签的id属性获取标签对象，id是唯一的，所以获取到是单个标签对象。

  添加如下代码：

  ~~~html
  <script>
  //1. 获取Element元素
  
  //1.1 获取元素-根据ID获取
   var img = document.getElementById('h1');
   alert(img);
  </script>
  ~~~

  浏览器打开，效果如图所示：从弹出的结果能够看出，这是一个图片标签对象

  <img width="549" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/862de5dc-9a63-4e8e-b26e-d262f7b2cbd3">


- document.getElementsByTagName() :  根据标签的名字获取标签对象，同名的标签有很多，所以返回值是数组。

  添加如下代码:

  ~~~js
  //1.2 获取元素-根据标签获取 - div
  var divs = document.getElementsByTagName('div');
  for (let i = 0; i < divs.length; i++) {
       alert(divs[i]);
  }
  ~~~

  浏览器输出2次如下所示的弹框

 <img width="552" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/c786145c-ef76-4928-a5af-93e3d5d64972">


- document.getElementsByName() ：根据标签的name的属性值获取标签对象，name属性值可以重复，所以返回值是一个数组。

  添加如下代码：

  ~~~js
  //1.3 获取元素-根据name属性获取
  var ins = document.getElementsByName('hobby');
  for (let i = 0; i < ins.length; i++) {
      alert(ins[i]);
  }
  ~~~

  浏览器会有3次如下图所示的弹框：

  <img width="555" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/92fb954c-ce10-4c60-8d21-7ffc5f73ff37">


- document.getElementsByClassName() : 根据标签的class属性值获取标签对象，class属性值也可以重复，返回值是数组。

  添加如下图所示的代码：

  ~~~js
  //1.4 获取元素-根据class属性获取
  var divs = document.getElementsByClassName('cls');
  for (let i = 0; i < divs.length; i++) {
       alert(divs[i]);
  }
  ~~~

  浏览器会弹框2次，都是div标签对象

 <img width="551" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/cdaac4e7-fec0-46ba-9fc1-e91bd2b1449d">


- 操作属性

  那么获取到标签了，我们如何操作标签的属性呢？通过查询文档资料，如下图所示：

 <img width="833" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/8b43b02e-cdf5-4ea6-90f6-ba2be07b3d26">


  得出我们可以通过div标签对象的innerHTML属性来修改标签的内容。此时我们想把页面中的**传智教育替换成传智教育666**，所以要获取2个div中的第一个，所以可以通过下标0获取数组中的第一个div，注释之前的代码，编写如下代码：

  ~~~js
  var divs = document.getElementsByClassName('cls');
  var div1 = divs[0];
  
  div1.innerHTML = "传智教育666";
  ~~~

  浏览器刷新页面，展示效果如下图所示：

  <img width="190" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/b6b66c58-b045-4c12-bb46-d286aa1ad212">


  发现页面内容变成了传智教育666



完整代码如下：

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JS-对象-DOM</title>
</head>

<body>
    <img id="h1" src="img/off.gif">  <br><br>

    <div class="cls">传智教育</div>   <br>
    <div class="cls">黑马程序员</div>  <br>

    <input type="checkbox" name="hobby"> 电影
    <input type="checkbox" name="hobby"> 旅游
    <input type="checkbox" name="hobby"> 游戏
</body>

<script>
    //1. 获取Element元素

    //1.1 获取元素-根据ID获取
    // var img = document.getElementById('h1');
    // alert(img);

    //1.2 获取元素-根据标签获取 - div
    // var divs = document.getElementsByTagName('div');
    // for (let i = 0; i < divs.length; i++) {
    //     alert(divs[i]);
    // }


    //1.3 获取元素-根据name属性获取
    // var ins = document.getElementsByName('hobby');
    // for (let i = 0; i < ins.length; i++) {
    //     alert(ins[i]);
    // }


    //1.4 获取元素-根据class属性获取
    // var divs = document.getElementsByClassName('cls');
    // for (let i = 0; i < divs.length; i++) {
    //     alert(divs[i]);
    // }



    //2. 查询参考手册, 属性、方法
    var divs = document.getElementsByClassName('cls');
    var div1 = divs[0];
    
    div1.innerHTML = "传智教育666";

</script>
</html>
~~~

### 1.4.4 案例 ###

<img width="619" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/f43307d4-dfbd-4099-b270-e56873be4483">

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JS-对象-DOM-案例</title>
</head>

<body>
    <img id="h1" src="img/off.gif">  <br><br>

    <div class="cls">传智教育</div>   <br>
    <div class="cls">黑马程序员</div>  <br>

    <input type="checkbox" name="hobby"> 电影
    <input type="checkbox" name="hobby"> 旅游
    <input type="checkbox" name="hobby"> 游戏
</body>

<script>
    //1. 点亮灯泡 : src 属性值
    var img = document.getElementById('h1'); //获取元素对象
    img.src = "img/on.gif"; //调用元素对象的src属性改变他


    //2. 将所有div标签的内容后面加上: very good (红色字体) -- <font color='red'></font>
    var divs = document.getElementsByTagName('div');
    for (let i = 0; i < divs.length; i++) {
        const div = divs[i];
        div.innerHTML += "<font color='red'>very good</font>"; 
    }


    //3. 使所有的复选框呈现选中状态
    var ins = document.getElementsByName('hobby');
    for (let i = 0; i < ins.length; i++) {
        const check = ins[i];
        check.checked = true;//选中
    }

</script>
</html>
~~~

## 1.5 JavaScript事件
什么是事件呢？HTML事件是发生在HTML元素上的 “事情”，例如：

- 按钮被点击
- 鼠标移到元素上
- 输入框失去焦点
- ........

而我们可以给这些事件绑定函数，当事件触发时，可以自动的完成对应的功能。这就是事件监听。例如：对于我们所说的百度注册页面，我们给用户名输入框的失去焦点事件绑定函数，当我们用户输入完内容，在标签外点击了鼠标，对于用户名输入框来说，失去焦点，然后执行绑定的函数，函数进行用户名内容的校验等操作。JavaScript事件是js非常重要的一部分，接下来我们进行事件的学习。那么我们对于JavaScript事件需要学习哪些内容呢？我们得知道有哪些常用事件，然后我们得学会如何给事件绑定函数。所以主要围绕2点来学习：

- 事件绑定
- 常用事件

<img width="424" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/f4afc886-1c8d-44a3-b852-ed05982db7f4">

### 1.5.1 事件绑定

JavaScript对于事件的绑定提供了2种方式：

- 方式1：通过html标签中的事件属性进行绑定

  例如一个按钮，我们对于按钮可以绑定单机事件，可以借助标签的onclick属性，属性值指向一个函数。

  在VS Code中创建名为14. JS-事件-事件绑定.html，添加如下代码：

  ~~~html
  <input type="button" id="btn1" value="事件绑定1" onclick="on()">
  ~~~

  很明显没有on函数，所以我们需要创建该函数，代码如下：

  ~~~html
  <script>
      function on(){
          alert("按钮1被点击了...");
      }
  </script>
  ~~~

  浏览器打开，然后点击按钮，弹框如下：

<img width="562" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/856c0152-7846-419e-a867-1100763175ee">


  

- 方式2：通过DOM中Element元素的事件属性进行绑定

  依据我们学习过得DOM的知识点，我们知道html中的标签被加载成element对象，所以我们也可以通过element对象的属性来操作标签的属性。此时我们再次添加一个按钮，代码如下：

  ~~~html
  <input type="button" id="btn2" value="事件绑定2">
  ~~~

  我们可以先通过id属性获取按钮对象，然后操作对象的onclick属性来绑定事件，代码如下：

  ~~~js
  document.getElementById('btn2').onclick = function(){
      alert("按钮2被点击了...");
  }
  ~~~

  浏览器刷新页面，点击第二个按钮，弹框如下：

<img width="559" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/8670325f-0c1b-4034-9640-56af683dbdae">


  

  **需要注意的是：事件绑定的函数，只有在事件被触发时，函数才会被调用。**

  

  整体代码如下：

  ~~~html
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <meta http-equiv="X-UA-Compatible" content="IE=edge">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>JS-事件-事件绑定</title>
  </head>
  
  <body>
      <input type="button" id="btn1" value="事件绑定1" onclick="on()">
      <input type="button" id="btn2" value="事件绑定2">
  </body>
  
  <script>
      function on(){
          alert("按钮1被点击了...");
      }
  
      document.getElementById('btn2').onclick = function(){
          alert("按钮2被点击了...");
      }
  
  </script>
  </html>
  ~~~

### 1.5.2 常见事件
上面案例中使用到了 `onclick` 事件属性，那都有哪些事件属性供我们使用呢？下面就给大家列举一些比较常用的事件属性

| 事件属性名  | 说明                     |
| ----------- | ------------------------ |
| onclick     | 鼠标单击事件             |
| onblur      | 元素失去焦点             |
| onfocus     | 元素获得焦点             |
| onload      | 某个页面或图像被完成加载 |
| onsubmit    | 当表单提交时触发该事件   |
| onmouseover | 鼠标被移到某元素之上     |
| onmouseout  | 鼠标从某元素移开         |
| onekeydown  | 某个键盘的键被落下       |

在代码中提供了10. JS-事件-常见事件.html的文件，我们可以通过浏览器打开来观察几个常用事件的具体效果：

- onfocus:获取焦点事件，鼠标点击输入框，输入框中光标一闪一闪的，就是输入框获取焦点了

  <img width="822" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/f3b04761-1514-46a3-8ef4-456f7a68bfe1">


- onblur:失去焦点事件，前提是输入框获取焦点的状态下，在输入框之外的地方点击，光标从输入框中消失了，这就是失去焦点。

  <img width="833" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/c7d558e4-ab1b-417a-b57d-8dafb812b095">


其他事件的效果，同学们可以通过提供好的代码去演示，亲身体会事件在什么时候触发。

完整代码如下：

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JS-事件-常见事件</title>
</head>

<body onload="load()">

    <form action="" style="text-align: center;" onsubmit="subfn()">
        <input type="text" name="username" onblur="bfn()" onfocus="ffn()" onkeydown="kfn()">
        
        <input id="b1" type="submit" value="提交">

        <input id="b1" type="button" value="单击事件" onclick="fn1()">
    </form>  

    <br><br><br>

    <table width="800px" border="1" cellspacing="0" align="center" onmouseover="over()" onmouseout="out()">
        <tr>
            <th>学号</th>
            <th>姓名</th>
            <th>分数</th>
            <th>评语</th>
        </tr>
        <tr align="center">
            <td>001</td>
            <td>张三</td>
            <td>90</td>
            <td>很优秀</td>
        </tr>
        <tr align="center">
            <td>002</td>
            <td>李四</td>
            <td>92</td>
            <td>优秀</td>
        </tr>
    </table>

</body>

<script>
    //onload : 页面/元素加载完成后触发
    function load(){
        console.log("页面加载完成...")
    }

    //onclick: 鼠标点击事件
    function fn1(){
        console.log("我被点击了...");
    }

    //onblur: 失去焦点事件
    function bfn(){
        console.log("失去焦点...");
    }

    //onfocus: 元素获得焦点
    function ffn(){
        console.log("获得焦点...");
    }

    //onkeydown: 某个键盘的键被按下
    function kfn(){
        console.log("键盘被按下了...");
    }

    //onmouseover: 鼠标移动到元素之上
    function over(){
        console.log("鼠标移入了...")
    }

    //onmouseout: 鼠标移出某元素
    function out(){
        console.log("鼠标移出了...")
    }

    /*
    如果您只使用 console.log() 而不是 alert()，通常情况下，如果没有阻止表单的默认提交行为，页面将会刷新，
    这导致所有之前的控制台输出都会被清除，即使 console.log() 已经执行了。
    由于页面刷新速度通常很快，可能导致控制台的输出在您能看到之前就已经被清空了。
    使用 alert() 时，它实际上会阻止页面继续执行直到您关闭弹窗，因此页面不会立即刷新，您可以看到之前的 console.log() 输出
    */
    //onsubmit: 提交表单事件
    
    function subfn(){
        alert("表单被提交了...");
    }

</script>
</html>
~~~

### 1.5.3 案例

<img width="709" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/c7f02bdf-579c-4eb1-bbfb-e0818cc6ab57">

在VS  Code中创建名为16. JS-事件-案例.html的文件

需求分析：

**需求1**

- 需求：

  点击 “点亮”按钮 点亮灯泡，点击“熄灭”按钮 熄灭灯泡

- 分析：

  点击按钮的时候触发，所以我们需要绑定单击事件。不管是点亮还是熄灭，都是图片的变化，所以我们需要修改图片。但是修改图片我们还需要先获取标签图片标签对象。

- 步骤：

  - 首先给点亮按钮和熄灭按钮都绑定单击事件。分别绑定函数on()和off（）
  - 然后在js中定义on()和off()函数
  - on()函数中，通过id获取img标签对象，然后通过img标签对象的src属性切换点亮的图片
  - off()函数中，通过id获取img标签对象，然后通过img标签对象的src属性切换熄灭的图片

- 代码实现：

  事件绑定

  ~~~html
  <input type="button" value="点亮" onclick="on()"> 
  <input type="button"  value="熄灭" onclick="off()">
  ~~~

  on()和off()函数

  ~~~js
  //1. 点击 "点亮" 按钮, 点亮灯泡; 点击 "熄灭" 按钮, 熄灭灯泡; -- onclick
  function on(){
      //a. 获取img元素对象
      var img = document.getElementById("light");
      //b. 设置src属性
      img.src = "img/on.gif";
  }
  
  function off(){
      //a. 获取img元素对象
      var img = document.getElementById("light");
      //b. 设置src属性
      img.src = "img/off.gif";
  }
  ~~~

  
**需求2**

- 需求：

  输入框鼠标聚焦后，展示小写；鼠标离焦后，展示大写。

- 分析：

  聚焦和失焦的时候完成功能，所以我们需要给input标签绑定onfocus和onblur事件；我们要切换大小写，那么我们可定要获取原本输入框的内容，通过查询资料，需要使用input标签对象的value属性，然后进行大小写切换；切换完成我们需要重新填入，所以还是通过value属性来设置input标签输入框的内容

- 步骤:

  - 给input标签的onfocus和onblur事件分别绑定lower()和upper()函数
  - 然后在js中定义lower()和upper()函数
  - 对于lower()函数，先通过id获取输入框对象，然后通过输入框的value属性来设置内容，内容的话可以通过字符串的toLowerCase()函数来进行小写转换
  - 对于upper()函数，先通过id获取输入框对象，然后通过输入框的value属性来设置内容，内容的话可以通过字符串的toupperCase()函数来进行大写转换

- 代码实现：、

  事件绑定：

  ~~~html
  <input type="text" id="name" value="ITCAST" onfocus="lower()" onblur="upper()">
  ~~~

  lower()和upper()函数

  ~~~js
  //2. 输入框聚焦后, 展示小写; 输入框离焦后, 展示大写; -- onfocus , onblur
  function lower(){//小写
      //a. 获取输入框元素对象
      var input = document.getElementById("name");
  
      //b. 将值转为小写
      input.value = input.value.toLowerCase();
  }
  
  function upper(){//大写
      //a. 获取输入框元素对象
      var input = document.getElementById("name");
  
      //b. 将值转为大写
      input.value = input.value.toUpperCase();
  }
  ~~~

  

**需求3**

- 需求：

  点击 “全选”按钮使所有的复选框呈现被选中的状态，点击 “反选”按钮使所有的复选框呈现取消勾选的状态。

- 分析：

  点击按钮完成功能，所以我们需要给2个按钮绑定单击事件；我们需要设置所有复选框的状态，通过我们之前的案例，我们知道，我们需要获取所有的复选框，然后遍历，可以通过设置checked属性为true，来设置复选框为选中；那么反之，设置checked属性为false，来设置复选框为未选中。

- 步骤：

  - 给全选和反选按钮绑定单击事件，分别绑定函数checkAll()和reverse()
  - 在js中定义checkAll()和reverse()函数
  - 对于checkAll()函数，首先通过name属性值为hobby来获取所有的复选框，然后遍历复选框，设置每个复选框的checked属性为true即可
  - 对于reverse()函数，首先通过name属性值为hobby来获取所有的复选框，然后遍历复选框，设置每个复选框的checked属性为false即可

- 代码实现：

  事件绑定：

  ~~~html
  <input type="button" value="全选" onclick="checkAll()"> 
  <input type="button" value="反选" onclick="reverse()">
  ~~~

  checkAll()和reverse()函数

  ~~~js
   //3. 点击 "全选" 按钮使所有的复选框呈现选中状态 ; 点击 "反选" 按钮使所有的复选框呈现取消勾选的状态 ; 
  function checkAll(){
      //a. 获取所有复选框元素对象
      var hobbys = document.getElementsByName("hobby");
  
      //b. 设置选中状态
      for (let i = 0; i < hobbys.length; i++) {
          const element = hobbys[i];
          element.checked = true;
      }
  
  }
      
  function reverse(){
      //a. 获取所有复选框元素对象
      var hobbys = document.getElementsByName("hobby");
  
      //b. 设置未选中状态
      for (let i = 0; i < hobbys.length; i++) {
          const element = hobbys[i];
          element.checked = false;
      }
  }
  ~~~

  

**完整代码**

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JS-事件-案例</title>
</head>
<body>

    <img id="light" src="img/off.gif"> <br>

    <input type="button" value="点亮" onclick="on()"> 
    <input type="button"  value="熄灭" onclick="off()">

    <br> <br>

    <input type="text" id="name" value="ITCAST" onfocus="lower()" onblur="upper()">
    <br> <br>

    <input type="checkbox" name="hobby"> 电影
    <input type="checkbox" name="hobby"> 旅游
    <input type="checkbox" name="hobby"> 游戏
    <br>

    <input type="button" value="全选" onclick="checkAll()"> 
    <input type="button" value="反选" onclick="reverse()">

</body>

<script>

    //1. 点击 "点亮" 按钮, 点亮灯泡; 点击 "熄灭" 按钮, 熄灭灯泡; -- onclick
    function on(){
        //a. 获取img元素对象
        var img = document.getElementById("light");

        //b. 设置src属性
        img.src = "img/on.gif";
    }

    function off(){
        //a. 获取img元素对象
        var img = document.getElementById("light");

        //b. 设置src属性
        img.src = "img/off.gif";
    }



    //2. 输入框聚焦后, 展示小写; 输入框离焦后, 展示大写; -- onfocus , onblur
    function lower(){//小写
        //a. 获取输入框元素对象
        var input = document.getElementById("name");

        //b. 将值转为小写
        // 字符串方法 .toLowerCase() 不会改变原始字符串，而是返回一个新的转换后的字符串
        // 将这个新字符串赋值回input.value,input是输入框对象，调用input.value方法重新设置输入框的当前值
        // input.value 本身是用来获取或设置输入框（即 input 输入框对象）的当前值的
        input.value = input.value.toLowerCase();
    }

    function upper(){//大写
        //a. 获取输入框元素对象
        var input = document.getElementById("name");

        //b. 将值转为大写
        input.value = input.value.toUpperCase();
    }



    //3. 点击 "全选" 按钮使所有的复选框呈现选中状态 ; 点击 "反选" 按钮使所有的复选框呈现取消勾选的状态 ; -- onclick
    function checkAll(){
        //a. 获取所有复选框元素对象
        var hobbys = document.getElementsByName("hobby");

        //b. 设置选中状态
        for (let i = 0; i < hobbys.length; i++) {
            const element = hobbys[i];
            element.checked = true;
        }

    }
    
    function reverse(){
        //a. 获取所有复选框元素对象
        var hobbys = document.getElementsByName("hobby");

        //b. 设置未选中状态
        for (let i = 0; i < hobbys.length; i++) {
            const element = hobbys[i];
            element.checked = false;
        }
    }



</script>
</html>
~~~

# 2 Vue
## 2.1 Vue概述
通过我们学习的html+css+js已经能够开发美观的页面了，但是开发的效率还有待提高，那么如何提高呢？我们先来分析下页面的组成。一个完整的html页面包括了视图和数据，数据是通过请求 从后台获取的，那么意味着我们需要将后台获取到的数据呈现到页面上，很明显， 这就需要我们使用DOM操作。正因为这种开发流程，所以我们引入了一种叫做**MVVM(Model-View-ViewModel)的前端开发思想**，即让我们开发者更加关注数据，而非数据绑定到视图这种机械化的操作。那么具体什么是MVVM思想呢？

MVVM:其实是Model-View-ViewModel的缩写，有3个单词，具体释义如下：

- Model: 数据模型，特指前端中通过请求从后台获取的数据
- View: 视图，用于展示数据的页面，可以理解成我们的html+css搭建的页面，但是没有数据
- ViewModel: 数据绑定到视图，负责将数据（Model）通过JavaScript的DOM技术，将数据展示到视图（View）上

如图所示就是MVVM开发思想的含义：

<img width="660" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/a049a4cb-0a40-4fb6-bdf1-7fc6e4d1a5f6">

基于上述的MVVM思想，其中的Model我们可以通过Ajax来发起请求从后台获取;对于View部分，我们将来会学习一款ElementUI框架来替代HTML+CSS来更加方便的搭建View;而今天我们要学习的就是侧重于ViewModel部分开发的vue前端框架，用来替代JavaScript的DOM操作，让数据展示到视图的代码开发变得更加的简单。可以简单到什么程度呢？可以参考下图对比：

<img width="872" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/ef84a212-4213-4a44-8c85-aae5b4101ce8">

在更加复杂的dom操作中，vue只会变得更加的简单！在上述的代码中，我们看不到之前的DOM操作，因为vue全部帮我们封装好了。


接下来我们来介绍一下vue。

Vue.js（读音 /vjuː/, 类似于 **view**） 是一套构建用户界面的 **渐进式框架**。与其他重量级框架不同的是，Vue 采用自底向上增量开发的设计。Vue 的核心库只关注视图层，并且非常容易学习，非常容易与其它库或已有项目整合。Vue.js 的目标是通过尽可能简单的 API 实现**响应的数据绑定**和**组合的视图组件**。

框架即是一个半成品软件，是一套可重用的、通用的、软件基础代码模型。基于框架进行开发，更加快捷、更加高效。

## 2.2 快速入门

<img width="774" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/88d50992-dea8-45af-aa99-a4eae297ed7d">

接下来我们通过一个vue的快速入门案例，来体验一下vue。

第一步：在VS Code中创建名为12. Vue-快速入门.html的文件，并且在html文件同级创建js目录，将**资料/vue.js文件**目录下得vue.js拷贝到js目录，如下图所示：

![1668858952627](assets/1668858952627.png) 

<img width="751" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/a72f31b4-5387-4a3f-8e49-8919c74db938">


第二步：然后编写&lt;script&gt;标签来引入vue.js文件，代码如下：

~~~html
<script src="js/vue.js"></script>
~~~

第三步：在js代码区域定义vue对象,代码如下：

~~~html
<script>
    //定义Vue对象
    new Vue({
        el: "#app", //vue接管区域
        data:{
            message: "Hello Vue"
        }
    })
</script>
~~~

在创建vue对象时，有几个常用的属性：

- el:  用来指定哪儿些标签受 Vue 管理。 该属性取值 `#app` 中的 `app` 需要是受管理的标签的id属性值
- data: 用来定义数据模型
- methods: 用来定义函数。这个我们在后面就会用到

第四步：在html区域编写视图，其中{{}}是插值表达式，用来将vue对象中定义的model展示到页面上的

~~~html
<body>
    <div id="app">
        <input type="text" v-model="message">
        {{message}}
    </div>
</body>
~~~

浏览器打开效果如图所示：

![1668859214102](assets/1668859214102.png) 



整体代码如下：

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Vue-快速入门</title>
    <script src="js/vue.js"></script>
</head>
<body>

    <div id="app">
        <input type="text" v-model="message">
        {{message}}
    </div>

</body>
<script>
    //定义Vue对象
    new Vue({
        el: "#app", //vue接管区域
        data:{
            message: "Hello Vue"
        }
    })
</script>
</html>
~~~

## 2.3 Vue指令
在上述的快速入门中，我们发现了html中输入了一个没有学过的属性`v-model`，这个就是vue的**指令**。

**指令：**HTML 标签上带有 v- 前缀的特殊属性，不同指令具有不同含义。例如：v-if，v-for…

在vue中，通过大量的指令来实现数据绑定到视图的，所以接下来我们需要学习vue的常用指令，如下表所示：

| **指令**  | **作用**                                            |
| --------- | --------------------------------------------------- |
| v-bind    | 为HTML标签绑定属性值，如设置  href , css样式等      |
| v-model   | 在表单元素上创建双向数据绑定                        |
| v-on      | 为HTML标签绑定事件                                  |
| v-if      | 条件性的渲染某元素，判定为true时渲染,否则不渲染     |
| v-else    |                                                     |
| v-else-if |                                                     |
| v-show    | 根据条件展示某元素，区别在于切换的是display属性的值 |
| v-for     | 列表渲染，遍历容器的元素或者对象的属性              |


### 2.3.1 v-bind和v-model
我们首先来学习v-bind指令和v-model指令。

| **指令** | **作用**                                       |
| -------- | ---------------------------------------------- |
| v-bind   | 为HTML标签绑定属性值，如设置  href , css样式等 |
| v-model  | 在表单元素上创建双向数据绑定                   |

- v-bind:  为HTML标签绑定属性值，如设置  href , css样式等。当vue对象中的数据模型发生变化时，标签的属性值会随之发生变化。

  接下来我们通过代码来演示。

  首先我们在VS Code中创建名为13. Vue-指令-v-bind和v-model.html的文件，然后准备好如下代码：

  ~~~html
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <meta http-equiv="X-UA-Compatible" content="IE=edge">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>Vue-指令-v-bind</title>
      <script src="js/vue.js"></script>
  </head>
  <body>
      <div id="app">
  
          <a >链接1</a>
          <a >链接2</a>
  
          <input type="text" >
  
      </div>
  </body>
  <script>
      //定义Vue对象
      new Vue({
          el: "#app", //vue接管区域
          data:{
             url: "https://www.baidu.com"
          }
      })
  </script>
  </html>
  ~~~

  在上述的代码中，我们需要给&lt;a&gt;标签的href属性赋值，并且值应该来自于vue对象的数据模型中的url变量。所以编写如下代码：

  ~~~html
  <a v-bind:href="url">链接1</a>
  ~~~

  在上述的代码中，v-bind指令是可以省略的，但是:不能省略，所以第二个超链接的代码编写如下：

  ~~~html
  <a :href="url">链接2</a>
  ~~~

  浏览器打开，2个超链接都可以点击，然后跳转到百度去！效果如图所示：

<img width="730" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/434646f9-198d-4d63-abbb-0e51a83738b5">


  

  **注意：html属性前面有:表示采用的vue的属性绑定！**

- v-model： 在表单元素上创建双向数据绑定。什么是双向？

  -  vue对象的data属性中的数据变化，视图展示会一起变化
  -  视图数据发生变化，vue对象的data属性中的数据也会随着变化。

  data属性中数据变化，我们知道可以通过赋值来改变，但是视图数据为什么会发生变化呢？**只有表单项标签！所以双向绑定一定是使用在表单项标签上的**。编写如下代码：

  ~~~html
  <input type="text" v-model="url">
  ~~~

  打开浏览器，我们修改表单项标签，发现vue对象data中的数据也发生了变化，如下图所示：

<img width="579" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/13477dd1-e30d-49ae-8ce1-c0a90e584235">



  通过上图我们发现，我们只是改变了表单数据，那么我们之前超链接的绑定的数据值也发生了变化，为什么？

  就是因为我们双向绑定，在视图发生变化时，同时vue的data中的数据模型也会随着变化。那么这个在企业开发的应用场景是什么？

  **双向绑定的作用：可以获取表单的数据的值，然后提交给服务器**
**注意：**
1. 通过v-bind或者v-model绑定的变量，必须在数据模型中声明。
  

  整体代码如下:

  ~~~html
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <meta http-equiv="X-UA-Compatible" content="IE=edge">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>Vue-指令-v-bind</title>
      <script src="js/vue.js"></script>
  </head>
  <body>
      <div id="app">
  
          <a v-bind:href="url">链接1</a>
          <a :href="url">链接2</a>
  
          <input type="text" v-model="url">
  
      </div>
  </body>
  <script>
      //定义Vue对象
      new Vue({
          el: "#app", //vue接管区域
          data:{
             url: "https://www.baidu.com"
          }
      })
  </script>
  </html>
  ~~~

### 2.3.2 v-on

<img width="749" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/a07e7504-aec4-49ec-9fb9-82bdf9251b13">

v-on: 用来给html标签绑定事件的。**需要注意的是如下2点**：

- v-on语法给标签的事件绑定的函数，必须是vue对象中声明的函数

- v-on语法绑定事件时，事件名相比较js中的事件名，没有on

  例如：在js中，事件绑定demo函数

  ~~~html
  <input onclick="demo()">
  ~~~

  vue中，事件绑定demo函数

  ~~~html
  <input v-on:click="demo()">
  ~~~

接下来我们通过代码演示。


在VS Code中创建名为19. Vue-指令-v-on.html的文件。
完整代码如下：
~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Vue-指令-v-on</title>
    <script src="js/vue.js"></script>
</head>
<body>
    <div id="app">

        <input type="button" value="点我一下" v-on:click="handle">
        <!-- 简化写法 -->
        <input type="button" value="点我一下" @click="handle()">

    </div>
</body>
<script>
    //定义Vue对象
    new Vue({
        el: "#app", //vue接管区域
        data:{
           
        },
        methods: {
            handle: function(){
                alert("你点我了一下...");
            }
        }
    })
</script>
</html>
~~~
### 2.3.3 v-if和v-show

<img width="942" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/8854f370-e025-48ea-8c32-b7ce1f9b4c4d">


我们直接通过代码来演示效果。在VS Code中创建名为15. Vue-指令-v-if和v-show.html的文件，提前准备好如下代码：

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Vue-指令-v-if与v-show</title>
    <script src="js/vue.js"></script>
</head>
<body>
    <div id="app">
        
        年龄<input type="text" v-model="age">经判定,为:
        <span>年轻人(35及以下)</span>
        <span>中年人(35-60)</span>
        <span>老年人(60及以上)</span>

        <br><br>
    </div>
</body>
<script>
    //定义Vue对象
    new Vue({
        el: "#app", //vue接管区域
        data:{
           age: 20
        },
        methods: {
            
        }
    })
</script>
</html>
~~~

其中采用了双向绑定到age属性，意味着我们可以通过表单输入框来改变age的值。

需求是当我们改变年龄时，需要动态判断年龄的值，呈现对应的年龄的文字描述。年轻人，我们需要使用条件判断`age<=35`,中年人我们需要使用条件判断`age>35 && age<60`,其他情况是老年人。所以通过v-if指令编写如下代码：

~~~html
年龄<input type="text" v-model="age">经判定,为:
<span v-if="age <= 35">年轻人(35及以下)</span>
<span v-else-if="age > 35 && age < 60">中年人(35-60)</span>
<span v-else>老年人(60及以上)</span>
~~~

浏览器打开测试效果如下图：

<img width="440" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/3b0477a6-0e14-40cb-bb28-3cfbf2ce8aec">


v-show和v-if的作用效果是一样的，只是原理不一样。复制上述html代码，修改v-if指令为v-show指令，代码如下：

~~~html
年龄<input type="text" v-model="age">经判定,为:
<span v-show="age <= 35">年轻人(35及以下)</span>
<span v-show="age > 35 && age < 60">中年人(35-60)</span>
<span v-show="age >= 60">老年人(60及以上)</span>
~~~

打开浏览器，展示效果如下所示：

<img width="479" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/ee7ed822-cd29-4265-9f73-4a71431ec76a">


可以发现，浏览器呈现的效果是一样的，但是浏览器中html源码不一样。v-if指令，不满足条件的标签代码直接没了，而v-show指令中，不满足条件的代码依然存在，只是添加了css样式来控制标签不去显示。

### 2.3.4 案例
- 需求：

<img width="839" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/9c4beecc-e40d-4596-a44e-82ddc8556e82">


  如上图所示，我们提供好了数据模型，users是数组集合，提供了多个用户信息。然后我们需要将数据以表格的形式，展示到页面上，其中，性别需要转换成中文男女，等级需要将分数数值转换成对应的等级。

- 分析：

  首先我们肯定需要遍历数组的，所以需要使用v-for标签；然后我们每一条数据对应一行，所以v-for需要添加在tr标签上；其次我们需要将编号，所以需要使用索引的遍历语法；然后我们要将数据展示到表格的单元格中，所以我们需要使用{{}}插值表达式；最后，我们需要转换内容，所以我们需要使用v-if指令，进行条件判断和内容的转换

- 步骤：

  - 使用v-for的带索引方式添加到表格的&lt;tr&gt;标签上
  - 使用{{}}插值表达式展示内容到单元格
  - 使用索引+1来作为编号
  - 使用v-if来判断，改变性别和等级这2列的值

- 代码实现：

  创建名为22. Vue-指令-案例.html的文件，完整代码如下：


## 2.4 生命周期
vue的生命周期：指的是vue对象从创建到销毁的过程。vue的生命周期包含8个阶段：每触发一个生命周期事件，会自动执行一个生命周期方法，这些生命周期方法也被称为钩子方法。其完整的生命周期如下图所示：

| 状态          | 阶段周期 |
| ------------- | -------- |
| beforeCreate  | 创建前   |
| created       | 创建后   |
| beforeMount   | 挂载前   |
| mounted       | 挂载完成 |
| beforeUpdate  | 更新前   |
| updated       | 更新后   |
| beforeDestroy | 销毁前   |
| destroyed     | 销毁后   |

下图是 Vue 官网提供的从创建 Vue 到效果 Vue 对象的整个过程及各个阶段对应的钩子函数：
<img width="894" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/7574578e-52db-48d5-990e-453ad895e02e">

其中我们需要重点关注的是**mounted,**其他的我们了解即可。

mounted：挂载完成，Vue初始化成功，HTML页面渲染成功。**以后我们一般用于页面初始化自动的ajax请求后台数据**

我们在VS Code中创建名为23. Vue-生命周期.html的文件编写代码来演示效果
完整代码如下：
~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Vue-指令-v-for</title>
    <script src="js/vue.js"></script>
</head>
<body>
    <div id="app">

    </div>
</body>
<script>
    //定义Vue对象
    new Vue({
        el: "#app", //vue接管区域
        data:{
           
        },
        methods: {
            
        },
        mounted () {
            alert("vue挂载完成,发送请求到服务端")
        }
    })
</script>
</html>
~~~
浏览器打开，运行结果如下：我们发现，自动打印了这句话，因为页面加载完成，vue对象创建并且完成了挂载，此时自动触发mounted所绑定的钩子函数，然后自动执行，弹框。()

<img width="559" alt="image" src="https://github.com/laurarian/java-tutorial/assets/78458931/019ce1bc-ad3b-4e4a-b2a3-9aebb4380797">

