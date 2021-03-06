---
layout: post
title: "About Javascript Function"
description: ""
category: Javascript 
tags: [Javascript, function, ruby, 函数式]
---

####一切皆是对象
函数在诸如python以及ruby的动态语言当中被当作是一等公民，相比叫静态语言，在这些语言当中函数可以不依托在任何的类或者实例，即可定义和调用。在web前端交互面向对象语言javascript同样具有这样的语言能力，因此我们可以这样来定义和调用一个function:

    //定义   
    var addMoney = function(count,callback){
      // add money
         callback(count);
    }

    //调用
    addMoney(100, function(count){console.log(''You have  added "+ count )});

变量addMoney 接收从function关键字返回的function对象， 既然是对象那么很自然我们可以把它当成另外一个方法的参数进程传递，例如：

    var printLog function(count){ console.log("A transaction was commit")}

    function DrawMoney(count, callback){
        callback(count);
    }

    drawMoney(40612002,printLog); 

####灵活的调用方式
关于函数调用，静态语言当中我们或者是通过类或者是通过对象实例或者是通过委托，但无一不是类型确定的。如果是静态方法，那么只能通过类来调用，如果是实例方法那么只能由实例对象来调用。所用函数的上下文在编译时就已经确定了：

    public class Guy{
       public string Name{public get;private set;}
       public int Age{public get; private set;}

       public Guy(string name, int age){
           this.Name=name;
           this.Age=age;
       }

       public void Say(){
           Console.Write(this.Name + this.Age);
      }
    }

    Guy guy= new Guy('"Jason", 25);
    guy.Say();

以上是C#的一个函数调用，调用实例guy实例方法Say，在Say的方法体内引用了this的实例变量Name，Age，很显然这个this就是guy实例对象。对于实例方法Say的调用只能通过实例而不能有其他的方法。我们不能通过类Guy.Say()来直接调用.
相比较而言javascript的函数调用则要灵活的多，但也增加了复杂度：

    var say = function( ){
        console.log( this.name + “say hello to you ”);
    }

    say();

如果直接在浏览器中运行发现this是window对象， 

我们可以通过设置属性把say加到某个对象当中，作为实例方法：

    //define a function named 'say'
    var say = function( ){
        console.log( this.name + “say hello to you ”);
    }

    // Set say to an object 
    var guy ={
        name: "Jason",
        age: 25,
        say:say
    }

    guy.say();

运行以上代码，我们看到的结果是输出对象guy的name，调用着是对象guy。代码中say是定义在guy上的实例方法，调用着自然是guy，如果不是作为guy的实例方法，则情况会有所不同：

    var say = function( ){
        console.log( this.name + “say hello to you ”);
    }

    var guy ={
        name: "Jason",
        age: 25,
        say: function(){say()}
    }

    guy.say();

运行以上代码， 我们不难看出这个this仍然是window，say()的调用实际是调用window.say(), 因为say()是定义在window中的一个全局变量。 

上面的代码是将say方法静态的加入到具体的对象中，从而达到引用实例的目的。 但是如果需要添加的实例很多，并且say方法显现出多态特性的时候，静态的添加就显得很不优雅。幸好javascript为每个function对象提供call和apply两个内置的方法来访问引用的对象：

    var say = function( ){
        console.log( this.name + “say hello to you ”);
    }

    var guy ={
        name: "Jason",
        age: 25
    }

    say.apply(guy)


#####function的特殊用法，构造函数  


一个函数有两种被调用方式,：
普通的调用方式，就如我们上面调用function的方式，下面我们来看一个比较文艺的调用，也就是作为构造函数返回一个对象：

    function Guy(name,age){
        this.name =name;
        this.age = age;
        this.say = function(){console.log(this.name+ "say hello to you")}
    }

    var guy = new Guy();
    guy.say();

作为c#或者java开发者也许你并不会怀疑这样的使用方式，因为我们太熟悉这样的写法。不过值得注意的是javascript不是使用class而是function来做到的，如何还不能引起你的怀疑那么给它做了一点点的修改：

    function Guy(name,age){
        this.name =name;
        this.age = age;
        this.say = function(){console.log(this.name+ "say hello to you")}
    }

    var guy = Guy();
    guy.say();

运行这段代码，guy.say() 将会报undefined method错误. 也许你已经注意到这里较之前少了一个new。 前后的结果大相径庭，看来这个new隐藏了不少秘密！ 

原来, 如果不加new关键字，那么实际上就是一个“普通”函数调用，函数有返回值则返回它，没有则返回null。 
如果使用new关键字， 则会当作构造函数，在内部进行对象的构造，并返回这个对象，为代码来大致描述构造的过程如下：

{% include JB/setup %}
