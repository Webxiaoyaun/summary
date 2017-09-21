## web标准的理解
- web标准是由网页有结构，表现，行为构成！
- 结构的标准
 - XML+XHTML到目前的html5都有差异
- 表现的标准
  - css2标准到现在css3的新属性，兼容
- 行为
- dom+javascript


## 浏览器的内核差异
- 目前市场上基本有4大内核
- Trident 典型代表IE浏览器，网页的标准兼容性不好

- Gecko 典型代表火狐浏览器 功能强大

- Webkit 典型代表谷歌浏览器，基本安卓和苹果手机上都是这个

- Presto Opera浏览器，这个在市场上份额很少，但是linux系统上很完美


## hack

- 针对所有IE：<!--[if IE]>....<![endif]-->
- 针对IE9及以下版本：<!--[if lt IE 9]>....<![endif]-->
- 我们可以给浏览器每个版本的写上css的类，然后通过类来在特定的浏览器版本生效
- <!--[if IE 7 ]><html class="ie7" lang="zh-cn"><![endif]-->
- <!--[if IE 8 ]><html class="ie8" lang="zh-cn"><![endif]-->
- <!--[if IE 9 ]><html class="ie9" lang="zh-cn"><![endif]-->
- <!--[if (gt IE 9)|!(IE)]><!--><html class="" lang="zh-cn"><!--<![endif]-->
  -例如 .ie7 .content{}
  
## css布局
- 我们可以把结构和表现分离开，
- 便于我们后期维护

## 盒子模型
- 盒子模型有4个属性
  - 外边距 margin
  - 内边距 padding
  - 边框 border
  - 内容部分 content
- IE盒子
  - 内容content的width包括了内边距和边框
  
## 选择器的优先级

- ！important 这个最高级
 -  color:blue !important;
 
- style 优先级第二
 - style="color:red"
 
- id  优先级第三
 - #color{color:red}
- :nth-child(3)选择符 优先级第四
- p:nth-child(3)

- 类选择符  优先级第五
- .color{color:red}

- 标签选择符 优先级第六
- div{color:red}

- 通配符选择符 优先级第七
- *{margin:0;padding:0}


## html5
- html5新增加的标签，很语义化
  - header
  - footer
  - nav
  - section
  - aside  不重要
  - atrical 不重要
  
- 重要的标签
  - video 视频
  - audio 音乐
  - canvas 画布
  
- 新增加的表单新属性
 - placehplder  提示
 - required 必填
 - tel 电话
 - date 日期
 - number 数字
 - color 颜色


## css3 
- 样式
- border-radius  圆角
- box-shadow 阴影
- background-size 北京图片尺寸
- text-shadow 文本阴影
- linear-gradient 线性渐变

- 动画
#### transform 变形
- 单位deg
 - rotate(x) 旋转
   - 参数x必须是以deg结尾的角度数或0，可为负数表示反向。
   
   
 - scale 缩放
   - 单位是数字
   - 元素x和y方向均缩放a倍
   - transform: scale(a); 
  
   - 元素x方向缩放a倍，y方向不变
   - transform: scaleX(a); 
   
   -x方向不变,元素y方向缩放b倍
   - transform: scaleY(b); 
   
 - translate 平移
   - 单位px
   - 元素x方向位移a，y方向位移b
   - transform: translate(a, b);
    
   - 元素x方向位移a，y方向不变               
   - transform: translateX(a); 
   
   - 元素y方向位移b，x方向不变               
   - transform: translateY(b); 
                    
 - skew() 倾斜
 - 单位 deg
   - 元素x方向倾斜角度a
   - transform:skew(a,b)
   
   
####transition 过渡

  - transition-property
    - 作用与css样式 也可以all
 
  - transition-duration 
    - 过渡运行总时间
    - 10s
 
  - transition-delay
    - 过渡推迟多少秒执行
 
#### animation 动画
  - animation-name
  - 动画名字
  
  - animation-duration
  - 动画运行总时间
  
  - animation-delay
  - 动画延迟多长时间
  
  - animation-iteration-count
  - 动画执行次数，也可以循环执行 infinite
  
 - 定义一个动画 ,最后动画完成一定要100%
 - @-webkit-keyframes 动画名字{0%{}50%{}100%{}} 






## flex布局
- display: flex;
- flex 
  - 1 占当前比例的1份
  - 2 占当前比例的2份
  
- flex-direction 项目的排列方向
  - row 从下往上排
  - row-reverse 从上往下排
  - column 从左往右排
  - column-reverse  从右往左排
  
- flex-wrap 决定换不换行
  - wrap 换行
  - nowrap 不换行
  
- justify-content 对齐方式
  - center 横向居中对齐
  - flex-start 左边对齐
  - flex-end 右边对齐
  
- align-items 对齐方式
  - center 纵向对齐方式
  - flex-start 上边对齐
  - flex-end 下边对齐

## js数据类型
- null 不存在，连声明变量都没有
- undefined 未定义，声明变量了却没有值
- number 数字
- string 字符串
- boolean 布尔
- object 对象

## js运算
- 基本运算符
- + 加
- - 减
- * 乘
- / 除
- = 赋值
- ++ 累加
- -- 累减
- % 求余
- += 每次赋值累加
- -= 每次赋值累减

## js对象
- 定义一个对象
- let obj={}

## js 原型
- 每一个函数上都有一个属性叫prototype
- prototype 

## js 闭包
- 函数执行都会形成一个私有作用域，保护里面的私有变量不受外界干扰,这种保护叫闭包
 ```
 var a=10;
 function fe(){
    var a=666; //私有变量
    console.log(a);
 }
 a=10000; //全局
 fe() //666 私有的变量受保护，没有被全局影响
 console.log(a) //10000
 ```
 
## 继承 
 - es5 继承就是修改原型链
 
 - es6 a继承b的一些属性和方法
 - class a extends b{
      constructor(props){
       //调用实现父类的构造函数
        super(props);
      }
 }

## 作用域
- 作用就是保护变量
- {}

## 原型链
- _proto_是任何对象都有的属性

## 常用事件

- onclick 
- 点击事件

- onmouseover 
- 鼠标滑进

- onmouseoute
- 鼠标划出

- onload 
- 页面加载完成

- onkeydown
- 键盘按下

- onkeyup
- 键盘弹起

- onfocus
- 获取焦点

- onblur
- 失去焦点

- onchange
- 用户改变input输入或者select下拉框改变

- oninput
- 文本框中输入就执行

- ondblclick
- 双击

- onscroll
- 滚动

- onresize
- 浏览器的窗口重置大小就发生

- onselect
- 文本被选中

## 事件对象
- onclick(event)

- 触发事件的元素节点
- event.target 

- 阻止当前事件
e.cancelBubble=true;
- event.stopPropagation()

-  阻止默认行为
- e.preventDefault()

## 正则表达式
- RegExp
- 匹配三个数字
- new RegExp("/\d{3}$/")

- search()
- 检索字符串开始的位置

-match()
- value值.match(正则表达式)

- test()
- 正则表达式.test(value值)

## json
- json格式
- {}，{'':[{},{}]},[{},{}]等

- 将字符串转为json对象
- JSON.parse()

- 将json对象转为字符串
- JSON.stringify()

## DOM操作
- 创建一个标签
- document.createElement('div')

- 获取元素
  -根据id或者class获取元素
    - document.querySelector("#id"或者".class")
  - 根据id获取元素
    - document.getElementById()
  - 根据class名字获取
    - document.getElementsByClassName('class')
  - 根据标签获取
    - document.getElementsByTagName('table')
    
- 获取父元素
 - ele.parentNode
 
- 获取子元素
 - ele.children
 - 兼容写法
 - var ele.firstElementChild||ele.children[0];
 
- 获取当前元素的第一个子元素
 - ele.firstChild
 
- 获取当前元素的最后一个子元素
  - ele.firstElementChild
  
- 头部添加子元素
  - appendChild()

- 删除子元素
  - removeChild()
  
- 属性操作

 - 判断有没有这个类
 - ele.hasAttribute('class')
 
 - 移除属性
 - ele.removeAttribte('class')
 
 -获取属性
 - ele.getAttribte('class')
 
 -设置属性
 - ele.setAttribute('class','值')
 
 - 设置值
  - innerHTML  内部html
  - innerText  内部文本
  
  - outerHTML  外部HTML
  - outerText  外部文本
  
  
## BOM 浏览器对象
- window.history.go(-1) 返回上一个窗口页面

- setInterval 循环执行计时器
- clearInterval 暂停执行

- setTimeout 定时执行一次
- clearTimeout 暂停执行


- location.href 跳转页面


## 跨域

- 同源策略
 - 域名
 - 协议
 - 端口
- 违法上面的一个不同，就叫跨域

- jsonp
-  动态创建script请求，src写链接

- jquery的$ajax
  - dataType:'jsonp'

- fetch ，跨域和不跨域都不用设置
 ```
 let myHeaders = new Headers({
     'Access-Control-Allow-Origin': '*',
     'Content-Type': 'text/plain'
 });
 fetch(url, {
     method: 'GET',
     headers: myHeaders,
     mode: 'cors'
 }) .then((res) => {
     // TODO 
 })
 ```

## 异步加载
动态创建标签,然后插到body结束标签后
```
(function() { 
var s = document.createElement('script'); 
s.type = 'text/javascript'; 
s.async = true; 
s.src = 'http://yourdomain.com/script.js'; 
var x = document.getElementsByTagName('script')[0]; 
 x.parentNode.insertBefore(s, x); 
})();
```

## mvvm框架
- vue.js
 - vue-router 路由
 - vuex 状态管理
 
## mac框架
- react
- angular

## 响应式
- all代表所有设备
- screen 电脑显示器
- handled 便携设备
- media all and(min-width:1200px)


## 自动化构建工具
- webpack
- 以前老版的grunt,gulp没有必要细琢磨

## http状态码
   - 200:'ok', //成功
   - 206:'',  //部分类容
   - 301:'',  //永久重定向
   - 302:'', //临时重定向
   - 304:'', //缓存发现
   - 400:'', //客户端请求错误
   - 401:'',  // 未授权
   - 403:'',  // 登录之后，无权访问
   - 404:'',  //资源没有找到
   - 500:'',  //服务器端内部错误
   - 503:''  //服务暂时不可用
   

## html5本地存储
- localStorage 永久化本地存储，只要不主动删除 就会一直存在
- sessionStoage 会话级存储，关闭浏览器客户端，销毁存储

##### 设置存储
- localStorage.setItem('存储名字', 存储类容);
   - 将对象转为string再存储
   - localStorage.setItem('user',JSON.stringify({username:'老王'，ID:1}));
   - 获取存储
     - localStorage.getItem('user');
- 根据指定的key删除一个元素
  - localStorage.removeItem('username');
- 清空存储
localStoage.clear();

## web安全
- XSS
- CSRF 跨站伪造

## 可维护性
- 重复写的代码封装成一个，重复的功能模块化
- 结构样式必须分离开，整洁干净
- 重复操作构建工具去做
- 代码风格一致，可读性好，别人接手毫不费力

## 易用性
- 个人推崇页面简洁，操作简单，直观可见，重点突出
- 一种主调色彩，搭配少了的辅助相近色，合理布局，轻易突出需要表现的东西


## 职业生涯、快速学习能力
- 学习职业生涯不是每天重复你毫不费力的事情，
- 学会沟通，明确描述自己的问题，并大胆说出自己解决的思路，
调试现象，沟通和请教的时候态度谦虚点不是错，这是基本礼貌，学会
聆听别人的看法。

- 学会梳理自己技术结构，前端不止页面，后端也属于前端的一种技术，说
这句话不过分，前端越来越复杂，现在应该是全端了，后端不在局限于后端人员
学会接受市场变化，多学习对你职业发展有利的技术
- 
- 学习应该是一种习惯，自主不讨厌的进行，这不应该是一种
逼迫，应该是一种习惯，不应该有任何埋怨，因为学习是提高你更多了一种认知
，工作不是应付完成就行，多思考性能优化问题，多重方案的优缺点




## css布局
- 左边100px,右边100px，中间自适应
- flex布局 
- flex:0 0 100px
```
  .content{
            display: flex;
            height: 20px;
            border:1px solid #eeeeee;

        }
        .left{
            width: 100px;
            height: 20px;
            flex-grow: 0;
            flex-shrink: 0;
            flex-basis: 100px;
            background: red;
        }
        .center{
            flex: 1;
        }
        .right{
            width: 100px;
            height: 20px;
            flex-grow: 0;
            flex-shrink: 0;
            flex-basis: 100px;
            background: red;
        }
```
- calc 计算
```
 .content{
            width: 100%;
            height: 20px;
            border:1px solid #eeeeee;

        }
        .content:after{
            display: block;
            height: 0;
            clear: both;
        }
        .left{
            width: 100px;
            height: 20px;
            float: left;
            background: red;
        }
        .center{
           width:-webkit-calc(100% - 200px);
            width:-moz-calc(100% - 200px);
            width:calc(100% - 200px);
            height: 20px;
            float: left;

        }
        .right{
            width: 100px;
            height: 20px;
            float: left;
            background: red;

        }
```

- 浮动
```
<div style="width:100%; margin:0 auto;"> 

       <div style="width:200px; float:right; background-color:#960">这是右侧的内容 固定宽度</div>

       <div style="width:150px; float:left; background:#6FF">这是左侧的内容 固定宽度</div>

       <div style="margin-left:150px;margin-right:200px; background-color:#9F3">中间内容，自适应宽度</div>

    </div>
```
- 定位
```
      .left,.right{
            position: absolute;
            top:0;
            width: 200px;
            height: 20px;
            background: red;
        }
        .left{
            left: 0;

        }
        .center{
          margin: 0 200px;
            width: 100%;
        }
        .right{
           right: 0;

        }
```
## 左侧菜单栏占300px，右侧内容可以根据浏览器自适应
- 解决思路现在提供两个
- flex 和calc

```
 .content{
            width: 100%;
            height: 20px;
            border:1px solid #eeeeee;
            display: flex;
        }
        .left{
            width:100px;
            height: 20px;
            flex: 0 0 100px;
            background: red;

        }
        .right{
            flex:1;
        }

```
## CSS选择器又哪些？有哪些新特性？有哪些伪类？
- id选择器 (#myid)
- 类选择器 (.className)
- 标签选择器  (div)
- 相邻选择器  (h1+p)
- 子选择器   (ul>li)
- 后代选择器  (li a)
- 通配符选择器  (*)
- 属性选择器   (input[type="text"])
- 伪类选择器  (a:hover,li:nth-child())

- 伪类
  - :active 
  - 鼠标点击，增加特效，鼠标松开，特效消失，多用在按钮上
  - :hover
  - 鼠标划入标签，增加特效，鼠标松开，特效消失
  - :focus
  - 我们点击元素后想一直拥有某些样式，多用于input标签有焦点时候
  
  - :first-child
  - 对元素第一个子元素添加样式
  
  - :nth-child(index)
  - 对元素第几个添加样式
  
  - :before和after
  - 多用于消除元素浮动
  
  

## 清除浮动
- clear:both
- 结尾处加空div标签设置clear:both

- 父级标签定义伪类:after给样式来消除
````
.clearfloat:after{
display:block;
clear:both;
content:"";
visibility:hidden;
height:0;
}
//针对IE
.clearfloat{
zoom:1
}
````

- 父级div设置overflow:hidden

- 父级div定义display:table



## div里面图片设置垂直居中
- 首先设置div为table-cell
```
div{
    width:100%;
    height:100%:
    position: fixed;
    display:table-cell;
    vertical-align:center;
}
img{
    width:100px;
    height:100px
}
```

- 第二种定位设置
```
div {
    width:100%;
    height:500px;
    position:relative;
}
img{
     width:100px;
     height:100px;
     position:absolute;
     top:50%;
     left:50%;
     margin-top:-50px;
     margin-left:-50%;
}
```

- 第三中transform: translate(-50%.-50%)
```
 .div{
    width:100%;
    height:100%;
    border:1px solid black;
    position: fixed;
    background-color: rgba(0,0,0,0.5); 
    }
 img{
     position:absolute;
     width:50px;
     height:50px;
     top:50%;
     left:50%;     
     -webkit-transform: translate(-50%,-50%);
     -ms-transform: translate(-50%,-50%);
     -o-transform: translate(-50%,-50%);
     transform: translate(-50%,-50%);
      background:#22B14C;
}        
```


## 2级DOM
- addEventListener():可以为元素添加多个事件处理程序，触发时会按照添加顺序依次调用。 
- removeEventListener() 移除事件

##DOM事件捕获和冒泡的具体流程
- 事件捕获阶段
  - 事件从最上一级标签开始往下找，直到捕获到事件目标（target）
  
- 事件冒泡阶段
  - 事件从事件目标（target）开始，往上冒泡到页面最上一级标签
  
- 阻止冒泡
 - IE下设置cancelBubble = true；
 - event.stopPropagation()
 
- 一般也就点击事件冒泡多一点


## Event对象的常见应用场景

- 一个完整的事件系统，一般存在3个角色
  - 事件对象  用来储存事件状态
  - 事件源对象  当前事件在操作的对象
  - 事件监听  当一个事件源生成一个事件对象时，它会调用相应的回调函数进行操作
 
- event.target 当前事件目标元素

- preventDefault() 不要执行与事件关联的默认动作
- stopPropagation()	 阻止事件冒泡

- 获取event对象兼容写法
- event || (event = window.event);

- 获取target兼容写法
- event.target || event.srcElement

- 阻止浏览器默认行为兼容写法
- event.preventDefault ? event.preventDefault() : (event.returnValue = false);

- 阻止冒泡写法
- event.stopPropagation ? event.stopPropagation() : (event.cancelBubble = true);


## 事件委托

- 事件委托就是利用事件冒泡，指定一个事件处理程序，管理
某一类型相同的所有事件

```
// 利用事件委托 比一个一个绑定事件 性能提高多倍
    var oUl = document.getElementById('oUl');
    var list = oUl.getElementsByTagName('li');
   
       // 利用事件委托 比一个一个绑定事件 性能提高多倍
       oUl.onclick = function (e) {
           e = e || window.event;
           var tar = e.target || e.srcElement;
           //tar 当前节点 <li></li>
           //tar.tagName当前标签名字li
           //toUpperCase()转为大写
           if(tar.tagName.toUpperCase() === 'LI'){
              console.log(tar.innerHTML);
           }
       }
```

## JS中常遇到的浏览器兼容问题
- 网页可见区域宽和高
- document.body.clientWidth||document.docuemntElement.clientWidth;
- document.body.clientHeight||document.docuemntElement.clientHeight;


- event事件对象
````
  document.onclick=function(ev){//兼容写法；
        var e=ev||window.event;
        var mouseX=e.clientX;//鼠标X轴的坐标
        var mouseY=e.clientY;//鼠标Y轴的坐标
    }
````
- event中的target
```
  document.onmouseover=function(e){
        var e=e||window.event;
        var Target=e.target||e.srcElement;//获取target的兼容写法，后面的为IE
        var from=e.relatedTarget||e.formElement;//鼠标来的地方，同样后面的为IE...
        var to=e.relatedTarget||e.toElement;//鼠标去的地方
    }
```
## js创建对象三种方式

- var obj={}
- var obj=new 函数名()
- var obj=new Object()


## js 继承的几种方式
- 原型链继承 ，私有，公有都继承
    - 将父类实例化后绑定在子类的原型上
    - 然后实例化子类，可以调用父类的方法
    
```
function Parent(name) {
    this.name = name
}
Parent.prototype.home = '北京';
function Child() {
    this.age = 8;
}
//将父类的实例绑定在子类的原型上
Child.prototype = new Parent('aa');
//实例化子类
let child = new Child();
//这时候继承父类的公有私有属性
console.log(child.home+child.name);
// 结果 北京 + aa
```

- 构造函数继承 ，私有继承，公有不继承
  - 在子类里面，call改变父类this
```
function Parent(name) {
    this.name = name
}
//父类的公有属性
Parent.prototype.home = '北京';

function Child(name) {
    this.age = 8;
    Parent.call(this,...arguments);

}
let child = new Child('hello');
console.log(child.home+child.name);

//结果是 undefined +hello
```
- 组合继承 公有继承，私有不继承
```
function Parent(name) {
    this.name = name
}
Parent.prototype.home = '北京';
function Child() {
    this.age = 8;
}
Child.prototype = Object.create(Parent.prototype);
let child = new Child();
//这时候继承只继承父类的公有属性 父类的私有属性没有继承
console.log(child.home+child.name);
// 结果 北京 + indefined
```
- es6继承
```
class Person {
    //控制器
    constructor(name,age){
        this.name=name;
        this.age=age;
    }
    eat(){
        console.log("吃饭");
    }
}
//关键字 extends 公私有都会继承
class Girl extends  Person{
    constructor(name,age){
        super(name,age); //默认调用父类，并且this就是girl实例
    }
}
let g=new Girl('aa',18);
console.log(g.name,g.age);
g.eat();
//结果aa 18
// 吃饭
```

## js合并两个对象
- Object.assign
```
var o1 = { a: 1 };
var o2 = { b: 2 };
var obj = Object.assign(o1, o2);
```

- jquery合并两个对象
 - $extend
```
a = {'a': 1};
b = {'b': 1};
c = $.extend(a, b)
```

- 事件绑定和普通事件的区别
  - 普通添加事件的方法不支持添加多个事件，最下面的事件会覆盖上面的，而事件绑定（addEventListener）方式添加事件可以添加多个。


- 高性能动态向一个div中插入1000个div标签
 - document.createdocumentfragment 文档碎片
 - 一次性拼接完字符串，最后一次插入节点，减少dom操作
 
```
  //先创建文档碎片

    var oFragmeng = document.createDocumentFragment();


    for(var i=0;i<1000;i++)

    {

        var op = document.createElement("div");

        var oText = document.createTextNode(i);

        op.appendChild(oText);

        //先附加在文档碎片中

        oFragmeng.appendChild(op);

    }


    //最后一次性添加到document中

    document.body.appendChild(oFragmeng);
```


## jquery.extend , jquery.fn.extend的区别
- jquery.extend 为jquery的扩展类
- jquery.fn.extend 给jquery对象添加方法
 - 大部分插件都用jquery.fn.extend
 
 
## jquery中的bind，live，delegate，on区别

- bind() 是直接绑定在元素上，如果没有设置阻止冒泡stopPropagatio
很有可能他所有父元素，祖宗元素都会受影响
- unbind() 解除绑定

- live() 通过冒泡方式绑定到元素上
- 基本淘汰了，阻止冒泡都不管用

- on() 这个最好
- off() 解除绑定


## document.ready和document.load和$(function(){})有什么区别

- ready比load先执行

- ready事件在DOM结构绘制完成之后就绘执行。这样能确保就算有大量的媒体文件没加载出来，JS代码一样可以执行

- load事件必须等到网页中所有内容全部加载完毕之后才被执行
- 如果一个网页中有大量的图片的话，则就会出现这种情况：网页文档已经呈现出来，但由于网页数据还没有完全加载完毕，导致load事件不能够即时被触发。

$(function(){}) 匿名函数，你可以当成$(document).ready(function(){})的简写


## $.data()和$('#aaa').data()各自作用是什么？有什么区别

- $('#aaa').data()向元素附加数据，或从元素中获取数据
```
//向元素中附加数据greeting
$("#btn1").click(function(){
  $("div").data("greeting", "Hello World");
});
//从元素中获取数据
$("#btn2").click(function(){
  alert($("div").data("greeting"));
});
```

## es6 箭头函数
-  首先箭头函数没有自己的this
- 如果你要当前函数的this,那么箭头函数不行

## async/await 解决回调函数嵌套问题

## 如何在项目中解析处理es6和es7代码
- babel

## promise方法
- Promise 类
- 两个参数
  - resolve成功
  - reject失败
- 提供then()回调方法
- Promise.all()并发执行方法

```
function buypack(){
    return new Promise((resolve,reject)=>{
        setTimeout(()=>{
            if(Math.random()>0.5){
                resolve('买')
            }else{
                reject('不买，被打死');
            }
        },Math.random()*10*1000)
    })
};
buypack().then((data)=>{
    console.log(data);
},(err)=>{
    console.log(err);
})
```


#### async和await异步操作

- async 和 await解决异步问题，基于primise

- 主要解决promise的then方法嵌套

- async和await这两个关键字一起使用

- await后面智能跟promise对象

> Promise.all()并发读取

```
//es7

let fs=require('fs');
function read(url) {
    //new Promise 需要传入一个executor 执行器
    //executor需要传入两个函数 resolve reject
    return new Promise((resolve,reject)=>{
        //异步读取文件
        fs.readFile(url,'utf8',function (err,data) {
            if(err){
                reject(err)
            }else{
                resolve(data);
            }
        })
    })
};

//async await 解决异步问题，基于promise
//async await这两个关键字一起使用
//await 后面只能跟promise对象
async function getData(){
    try{
        //Promise.all()并发读取
        let result =await Promise.all([read('name.txt'),read('age.txt')]);
        console.log(result);
    }catch (e){
        console.log(e);
    }
}
getData();

//Promise 解决多层嵌套，回调地狱
// 解决异步请求，同步结果的问题

```