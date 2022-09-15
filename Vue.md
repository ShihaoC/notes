# Vue

## 引入Vue

~~~HTML
<script src="https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js"></script>
~~~

## 创建Vue实例

~~~HTML
<div id="#app">
    {{message}}
</div>

<script>
	var app = new Vue({
		//el:element缩写
        el:"#app",
        data:{
            message="Hello Vue!!"
        }
    })
</script>
~~~

## 选择结构

条件是vue实例中data数据的返回值

- v-if if块

- v-else else块

- v-else-if else if 块

  ~~~html
  <div v-if="条件"></div>
  <div v-else-if="条件"></div>
  <div v-else></div>
  ~~~

## for循环

1. 遍历数组：v-for="对象名 in 数组名"

   ~~~html
   <div id="#app">
       <li v-for="item in items">
       	{{item.message}}
       </li>
   </div>
   
   <script>
   	var app = new Vue({
           el:"#app",
           data:{
               //items数组
               items:[
                   {message:'aa'},
                   {message:'bb'}
               ]
           }
       })
   </script>
   ~~~

## 事件处理

~~~html
<button class=".app" v-on:click="count += 1">
    {{count}}
</button>

<script>
	var app = new Vue({
        el:".app",
        data:{
            count:0
        }
    })
</script>
~~~

## 表单输入绑定

~~~html
<input type="text" v-model="ell"></input>

<div>
    {{ell}}
</div>

<script>
	var app = new Vue({
        el:".app",
        data:{
            ell:''
        }
    })
</script>
~~~




## Axios

~~~html
<!--引入Axios-->
<script src="https://unpkg.com/axios/dist/axios.min.js"></script>
<!--读取json文件-->
<script>
	var app = new Vue({
        el:"#app",
        data(){
            return{
                info:{
                    键:值
                }
            }
        }
        //钩子函数
        mounted(){
        	axios
            	.get("json的位置")
        	    .then(respone => this.info = respone.data)
    	}
    })
</script>
~~~

