# Vue

![image-20220925162800185](img/1.png)

渐进式JavaScript框架

~~~markdown
# 渐进式
	1、易用 HTML CSS JavaScript
	2、高效 开发前端页面非常高效
	3、灵活 开发灵活，多样性
# 总结
	vue属于JavaScript框架，简化js页面操作
	bootstrap是一个css框架，封装css	
# vue出现
	打破了前后端分离的现状 大家一直使用jQuery 可以让程序员很轻松的完成数据和试图的绑定   双向绑定 MVVM模式
# vue作者
	尤雨溪
# 前端发展史
	html + js  ===> html+css+jquery ===> vue(前后端分离) 发送json格式的请求 发送到后端 后端数据
~~~

# Vue入门

### 2.1下载vue.js

~~~js
//开发版本
//开发环境版本
<script src="https://cdn.jsdelivr.net/npm/vue@2.7.10/dist/vue.js"></script>
//生产版本
<script src="https://cdn.jsdelivr.net/npm/vue@2.7.10"></script>
~~~

### 2.2Vue的第一个入门应用

~~~html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <!-- 引入vue.js -->
    <script src="../lib/vue.js"></script>

</head>

<body>
    <div id="app">
        <!-- 差值表达式：{{属性名}} -->
        <h2>{{msg}}</h2>
        <h3>{{msg}}</h3>
        <div>
            {{msg}}
        </div>
        <div>{{count}}</div>
        <div>{{count+1}}</div>
        <h3>
            {{contant.toUpperCase()}}
            {{contant.length}}
        </h3>
    </div>
</body>

</html>
<script>
    //创建一个vue实例
    new Vue({
        el: "#app", //element 代表vue实例的作用范围
        data: {
            msg: "poiutyre",
            count: 0,
            contant: 'sadasdasd'
        }//自定义各种数据
    }); 
</script>
~~~

~~~markdown
# 总结
	1、一个页面只能存在一个Vue实例,不能创建多个Vue实例
	2、Vue实例中el属性 代表Vue实例的作用范围，如果想在vue实例的范围内使用 可以使用 {{data属性中的变量名}} 直接进行调用
	3、如果使用{{}}进行data的数据获取的时候，可以在{{}}取值语法中及逆行给各种运算逻辑运算相关方法进行使用
~~~

