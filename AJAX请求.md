~~~javascript
let data = "";

$.ajax({
    url:"path", //请求URL
    type:"get", //请求类型
    data:JSON.stringify(data), //临时存放位置
    success:(result)=>{ //请求成功函数
        console.log(result)
    },error:(e)=>{ //错误函数
        console.log(e)
    }
})
~~~

