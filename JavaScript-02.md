## JavaScript的运算符/循环分支控制语句/函数声明/数组

[TOC]

### 1.运算符

#### 1.1 基本运算符(+ - * /  %)

```javascript
//算数运算符
    var a = 6;
    var b = 2;
    console.log("a+b=",a+b);
    console.log("a-b=",a-b);
    console.log("a*b=",a*b);
    console.log("a/b=",a/b);
    console.log("a%b=",a%b);
    var c;
    c = a + b;
    console.log("c = a+b = ",c);
```

#### 1.2 自增自减运算符

```javascript
//自增自减运算符
    var a = 1;
    a++;
	a--;
    console.log("a = ",a);		// a=1
```

#### 1.3 关系运算符

- 非等值关系运算符	和	等值关系运算符
- ==      (等值符,先转换为相同类型再进行比较大小) 
- ===    (等同符,先比较类型,类型相同再比较值)

```javascript
//关系运算符  (非等值关系运算符  和  等值关系运算符)
    //比较关系
    var aaa = 3000;
    var bbb = 2000;
    console.log("a>b",a>b);    //true
    console.log("a>=b",a>=b);  //true
    console.log("a<b",a<b);    //false
    console.log("a<=b",a<=b);  //false
    console.log("a!=b",a!=b);  //true

    //等值关系   ==(等值符,先转换为相同类型再进行比较大小) 和  ===(等同符,先比较类型,类型相同再比较值)
    var aa = 1;
    var bb = true;
    var cc = "1";
    var dd = '1';
    var ee = "true";

    console.log("aa===bb",aa===bb);      //false
    console.log("aa==bb",aa==bb);        //true

    console.log("aa===cc",aa===cc);      //false
    console.log("aa==cc",aa==cc);        //true

    console.log("cc==dd",cc==dd);        //true
    console.log("cc===dd",cc===dd);      //true

	//NAN自己不等于自己,NAN与任意的字符进行数学运算结果还是NAN
	//基本数据类型同时向number靠拢,调用Number全局函数
	function testNumber(){
    var aaaa = "true";
    var bbbb = true;
    // alert(Number(aaaa));  //NaN
    alert(Number(bbbb));     // 1
    }
```

#### 1.4 逻辑运算符

```javascript
// 逻辑运算符  && || !
    var lisi = 160;
    var zhansan = 170;
    var wangwu = 180;
    var zhaoliu =190;

    //逻辑与运算  必须全部符合才为true
    console.log("zhaoliu>lisi && zhaoliu>wangwu",zhaoliu>lisi && zhaoliu>wangwu);

    //逻辑或运算  有一个成立就为true
    console.log("zhaoliu>lisi || lisi>zhansan",zhaoliu>lisi || lisi>zhansan);

    //逻辑非运算  对结果取反
    console.log("!(zhaoliu>lisi)",!zhaoliu>lisi);

    //与运算  包括 短路与(&&) 和 逻辑与(&)
    //或运算  包括 短裤或(||) 和 逻辑或(|)
```

#### 1.5 对象运算符



#### 1.6 位运算符



#### 1.7 其他运算符



### 2.逻辑判断语句

#### if...else...条件语句

- 条件语句基于不同条件执行不同的动作
- if...else...if...else...使用该语句选择多条代码块之一来执行

```javascript
if(){
	...     
}
else{
    ...
}
```

```html
<script type="text/javascript">
     var a = 10;
     //判断，真或者假？？？？
     if (a < 0){
       console.log("a < 0");
     } else {
       var b = 20;//全局变量
       console.log("a >= 0");
     }
     console.log(b);

     var c = 30;
     if (c > 30){
       console.log("c > 30");
     } else if (c == 30){
       console.log("c  == 30");
     } else {
       console.log("c  < 30");
     }    
    </script>
```

- 注意:     !   !   !   !

```html
var a = 40;
if (a > 30) {
      console.log("a > 30");
    } else if (a > 35) {
      console.log("a > 35");
    } else  if (a == 30) {
      console.log("a == 30");
    } else if (a < 30) {
      console.log("a < 30");
    }
<!--只打印 ａ > 30 不打印　a > 35 -->
```

```javascript
var a;
var a = "";		
var a = 0;
var a = NaN;
    // 隐式转换
    if (a){
      console.log("xxxx");
    } else {
      console.log("yyyy");
    }
<!--以上四种清空都打印　ｙｙｙｙ-->
```

#### switch...case...条件语句

- switch...case使用该语句选择多条代码块之一来执行
- switch是基于不同的条件执行不同的动作

```javascript
var week = 3;
//判断
switch(week){
     case 1:
    	alert("今天是星期一");
    	break;
    case 2:
    	alert("今天是星期二");
    	break;
    case 3:
    	alert("今天是星期三");
    	break;
    case 4:
    	alert("今天是星期四");
    	break;
    case 5:
    	alert("今天是星期五");
    	break;
    case 6:
    	alert("今天是星期六");
    	break;
    case 7:
    	alert("今天是星期日");
    	break;
  	default:
    	alert("出错了!");
    	break;
}
```

### 3.循环语句

#### for循环

```html
for(init; condition; increment){
    statement(s);
}

<!--条件可以省略，但是“;”不能省略-->
```

```javascript
for (;;){
  //死循环
  console.log("xxx");
  }

//a仍然属于全局变量
for (var a = 10; a > 0; a--){
   console.log(a);
  }
```



- Homework:分别使用for循环和while循环打印九九乘法表

```html
<!--for循环 第一种方法-->
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>九九乘法表</title>

  </head>
  <body>
    <h1>九九乘法表</h1>
    <script type="text/javascript">
    document.write("for循环九九乘法表" + "<br/>");
      var i,j;
      for (i = 1; i < 10; i++) {
        for (j = 1; j <= i; j++) {
          document.write(i + "*" + j + "=" + (i * j) + "\t");
        }
        document.write("<br/>");
      }
      document.write("while循环九九乘法表" + "<br/>");
      var m = 1, n;
      while(m < 10) {
        n = 1;
        while(n <= m){
          document.write(m + "*" + n + "=" + (m * n) + "\t");
          n++;
        }
        document.write("<br/>");
        m++;
      }
    </script>
  </body>
</html>
```

```html
<!--for 循环第二种方法-->
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>循环分支</title>
  </head>
  <body>
    <input id="btn" type="button" name="btn" value="测试事件">
    <script type="text/javascript">
    // onload 页面加载完毕之后
      onload = function(){
        //HTML DOM document对象
        //getElementById 返回对拥有指定 id 的第一个对象的引用。
        document.getElementById("btn").onclick = function(){
          // 九九乘法表
          var sHTML = "";
          sHTML = "<table>";
          for(var i = 1; i <= 9 ; i++){
            sHTML+="<tr>";
            for(var j=1 ; j<=i;j++){
              sHTML+="<td>" + i + " * " + j + " = " + i*j +"</td>";
            }
            sHTML+="</tr>";
          }
          sHTML+="</table>";

          document.write(sHTML);
        }
      }
    </script>
  </body>
</html>
```

```javascript
<!--冒泡排序法-->
var aNumber = [10,2,34,4,56,12,45,44,6,12,23,55];
var item=0;
for(var m = 0;m <= aNumber.length-2; m++){
   for(var n = m+1; n <= aNumber.length-1;n++){
       if(aNumber[m]>aNumber[n]){
          item=aNumber[m];
          aNumber[m]=aNumber[n];
          aNumber[n]=item;
       }
   
}
alert(aNumber);
```

#### while循环

```javascript
while (condition)
{
  ...code;
}
```

### 4.JavaScript函数声明

> ​	函数对任何语言来说都是一个核心的概念。**通过函数可以封装任意多条语句**,而且可以在任何地方、任何时候调用执行。
>
> ​	**函数是实现某个特定的功能的多条语句的有序集合。**
>
> ​	**函数：就是封装代码，实现代码的模块化！！！**
>
> 函数声明的三种方式:
>
> - 函数也是对象
> - 声明式
> - 赋值式

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>function函数声明</title>
    <script type="text/javascript">
      //函数也是对象
      var f1 = new Function("alert(zhansan);");

      //声明式
      function f2(){
        alert("lisi");
      };

      //赋值式
      var f3 = function(){
        alert("wangwu");
      };
      f3();//调用f3();

      
      function sayHello(uname){
        alert("早上好: " + uname);//uname类似与局部变量
      };
      //形式参数,实际参数,一般要求形式参数和实际参数的数目一致,而且要对应
      sayHello("lisi");

      function sayBack(){
        return("666666");
        //后面的代码不会被执行
        alert("999999");
      }
      var test=sayBack();
        alert(test);
    </script>
  </head>
  <body>
    <h1>函数声明</h1>
  </body>
</html>
```

```javascript
//javascript函数示例:

function sum(arg1,arg2){
  return arg1 + arg2;
}
sum(1,2);
```

#### 函数声明

```javascript
//函数声明(声明式)
function fun(){
  console.log("fun....");
}
fun();				//函数调用

//函数声明(赋值式)
var fun1 = function(){
  console.log("fun1....");
};
fun1();				//函数表达式的调用必须在定义之后
```

#### 函数声明提升

```javascript
	fun();			//调用函数
    /*
    js中的函数有个特点：声明提升。
    函数可以定义在可调用的任何位置，在javascript引擎解释运行该代码时，会
    自动将函数提升到该作用域的顶部！！！！！！
    */
    function fun(){
      console.log("fun......");
    }
```

#### 函数传参

```javascript
/*
   功能：打印输出
   形式参数：
   @arg1, 任意类型
   @arg2, 任意类型
   @arg3, 任意类型
   返回值：默认没有返回，undefined
   */
   function func(arg1,arg2,arg3){
    //具体代码
    console.log(arg1,arg2,arg3);	//没有显示返回，默认返回undefined
   }

   //函数调用,需要传入实际参数
   //如果参数没有传递，那么会有undefined默认值
   var result = func(1,2,3,4,5,5,1);
   console.log(result);			//当没有显示返回(return)，返回值是undefined
```

```javascript
/*
  功能：求和
  @arg1, number
  @arg2, number
  返回值：计算结果
  */

   function func2(arg1,arg2){

    //  return 返回之后函数立刻结束，return之后的代码不再运行
     return arg1 + arg2;
   }

   //将func2的返回值给result,接收返回值
    var result = func2(10,20);
    console.log(result);
```

### 5.数组

#### 数组的声明和长度

- length属性表示数组的长度，即数组中元素的个数
- 数组的索引从 0开始，数组的上下限为0,length-1;
- 和其它编程语言不同的是，javascript的数组的length是可变的
- 当length的属性设置的很大时，整个数组状态不会发生很大的变化，只是length的长度变化
- 当length的属性设置的很小时，原先数组中索引大于或等于length的元素的值都会丢失

```javascript
//数组的创建
      var a1 = new Array();   //空数组
      var a2 = new Array(2);  //长度为2
      var a3 = new Array("shangsan","lisi","wangwu");
      //打印数组信息
      console.log(a1 + "|" + a2 + "|" + a3);
	  //结果为:|,|shangsan,lisi,wangwu

      //简介的创建
      var aa1 = [];
      var aa2 = ["张珊","李四","王五"];
      console.log(aa1 + "||" + aa2);
	  //结果为:||张珊,李四,王五
```

```javascript
//数组的长度
      var a = ["aa","bb","cc","dd","ee","ff","hh"];
      //查看数组的长度
      console.log("a.length = ",a.length);

      //遍历数组
      for(i = 0;i < a.length;i++)
      {
        //打印数组中每个元素的值
        console.log("a" + "[" + i + "]" + "=" + a[i]);
      }
      //java arraylist linklist vector
      //数组的长度是可变的
      a.length=10;
      alert(a);
```

```javascript
//数组初始化可以同时有多种类型,number,string,date
var b = [1,"shangsan",new Date(),[1,2,3,4,5]];
alert(b);
```

#### 数组的操作

```javascript
//新建一个数组并初始化
var aArray = new Array();
var aArray1 = new Array(4);
var aTeam = ["aaa","bbb","ccc","ddd"];
//下标为0 的位置存入 数值1
aArray[0] = "aaa";
aArray[1] = "bbb";
aArray[2] = "ccc";
aArray[3] = "ddd";
// 输出aArray数组的长度
console.log("aArray.length : " + aArray.length);
// 输出下标为2的内容
console.log("aTeam[2] : " + aTeam[2]);

// 将数组转换为字符串
console.log("aTeam.toString() : " + aTeam.toString());

// 将字符串按照指定的间隔格式输出 join()
console.log("aTeam.join('-').toString():"+ aTeam.join("-").toString());

// 将数组中的内容逆序输出
console.log("aTeam.reverse().join('-').toString():"+ aTeam.reverse().join('-').toString());

// 将字符串转换为数组
var sString = "aaa-bbb-ccc";  //object类型

// 使用split()方法 将字符串中指定间隔的内容分离开
var aTeam1 = sString.split("-");

// 输出分离后的内容
console.log("sString.split('-') :" + aTeam1);

// 输出下标为1 的内容
console.log("aTeam1[1] :" + aTeam1[1]);

// 输出aTeam1的类型
console.log("typeof aTeam1 :" + typeof aTeam1);
```

#### 数组的常见方法

##### 数组元素的添加

- push:数组末尾
- unshift:数组开头

```javascript
//声明数组
var aa = ["a","b","c","d","e","f","g","h"];
//添加元素
aa.push("www");
aa.unshift("http");
```

##### 数组元素的移除

- pop:移除最后一个
- shift:移除开头第一个

```javascript
//声明数组
var aa = ["a","b","c","d","e","f","g","h"];
//添加元素
aa.push("www");
aa.unshift("http");
//移除元素
aa.pop("www");
aa.shift("http");
//打印数组
alert(aa);
```

##### 即可添加也可删除~splice

- splice:添加删除到数组的指定位置

```javascript
//声明数组
var aa = ["a","b","c","d","e","f","g","h"];

//既可以添加也可以删除
aa.splice(1,3);         //删除下标从1开始的三个元素
aa.splice(3,0,"http");  //从数组下标为3的地方添加一个元素，后面的元素下标依次加1
//打印数组
alert(aa);

//更改指定索引对应的值
aa[3] = 10;  //用10代替d
aa[4] = null;  //将e替换为null
//打印数组      
alert(aa);
```

##### 取出指定索引的字串~slice

- slice() 方法返回一个从开始到结束（**\*不包括结束***）选择的数组的一部分**浅拷贝**到一个新数组对象。例如:[2,8)从2到8,包括 2 不包括 8 .

##### 拼接数组~concat

##### 翻转字符串~reverse

##### 排序~sort

##### 更换间隔符~join("-")

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>数组的声明和长度</title>
    <script type="text/javascript">
      //声明数组
      var a = ["a","b","c","d","e","f","g","h"];
      
      //取出指定索引的子串 [1,3)
      var b = a.slice(1,3);
      alert(b);
      
      //拼接数组
      var c = a.concat(1,2,3,4,5);
      alert(c);

      //翻转字符串
      c.reverse();
      alert(c);

      //排序
      c.sort();
      alert(c.join("-"));
    </script>
  </head>
  <body>
    <h1>数组的声明和长度</h1>
  </body>
</html>
```

### 6.break-continue-return的用法

```javascript
onload = function(){
   document.getElementById("btn").onclick = function(){
     var iSum = 0;
     for(var i = 1; i < 101; i++)
     {
        if(i==5){
          // break;结束最近的循环
          // break;
          // continue是结束符合条件的本次循环
          // continue;
          // return 第一种用法 是跳出整个方法体
          // return;
          // return 第二种用法 是返回一个值
          i = A(i);
       }
       iSum+=i;
      }
      alert(iSum);
      function A(i){
          i+=5;
          return i;
       }
     }
}
```

