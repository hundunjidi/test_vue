<template>
    <!--结构-->
    <div class="demo">
        <h1>我的个人简介</h1>
        
        <!-- <p>名字：{{name}}</p>
        <p>学号：{{id}}</p>
        <p>年龄：{{age}}</p>
        
        <button @click="showTel">展示电话</button>
        <button @click="addAge">增加年龄</button>
        <button @click="changeName">改变姓名</button> -->
        
        <h2>书籍</h2>
        <p>书名：{{ name }}</p>
        <p>价格：{{ price }}</p>
        <button @click="changeBookName">修改书名</button>
        <button v-on:click="changeBookPrice">修改书价</button>
        <hr><!--绘制一条分割线 -->
        <p v-text="text1"></p>
        <p v-html="text1"></p>
        <p><input type="text" v-bind:placeholder="username"></p>
        <p><input type="password" :placeholder="password"></p>
    </div>
</template>
    
<script>
    export default {
        name:"Person"      
    };
</script>

<script setup>

    import {ref,reactive, toRefs, toRef} from 'vue'
    //逻辑
    // var name=ref('吴富康')
    // var id='0432220227'  
    // var age=ref(20)
    // var tel="123"
    // const text1="<span>满堂花醉三千客，一剑霜寒十四州</span>"
    const text1="<span>剑气纵横三万里，一剑霜寒十四州</span>"
    const username="这是用户名"
    const password="这是密码"

    const book=reactive({
        name:'一人之下',
        price:50
    })

    const {name,price}=toRefs(book) 
    //const bname=toRef(book,"name")
    
    // function showTel(){
    //     //console.log(tel)
    //     alert(tel)
    // }

    // function addAge(){
    //     age.value+=1
    // }

    // function changeName(){
    //     if(name.value=="吴富康"){name.value="张扬"}
    //     else{name.value="吴富康"}
    // }

    function changeBookName(){
        name.value="嘻嘻嘻"
    }
    function changeBookPrice(){
        price.value=100
    }

</script>

<style>
    /*样式*/ 
    .demo{
        text-align: center;
        font-size: 20px;
        color: green;
        background:rgb(165, 165, 213);
    }
</style>