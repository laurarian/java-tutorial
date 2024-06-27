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
### 1.4.4 BOM对象(Document Object Model 文档对象模型)
