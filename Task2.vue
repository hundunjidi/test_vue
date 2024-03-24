<template>
    <div class="demo3">
        <!-- .prevent阻止默认事件 -->
        <a href="https://h5mota.com/games/24/" @click.prevent="">24层魔塔</a> 
    </div>

    <div class="demo3" @click="show('父元素')">
        <button @click="show('子元素')">事件冒泡</button>
        <!-- .stop阻止事件冒泡 -->
        <button @click.stop="show('子元素')">阻止事件冒泡</button>
    </div>

    <!-- .capture事件捕获 -->
    <div class="demo3" @click.capture="show('父元素')">
        <button @click="show('子元素')">事件捕获</button>        
    </div>

    <!-- .stop执行一次 -->
    <div class="demo3">
        <button @click.once="show('执行一次')">执行</button>   
    </div>

    <!-- .self事件 -->
    <div class="demo3" @click="show('祖父元素')">祖父元素
        <div @click.self="show('父元素')">父元素
            <div @click="show('子元素')">子元素</div>
        </div>
    </div>

     <!-- 绑定按键 -->
    <div class="demo3">
        <input type="text" @keyup.enter.exact="show('绑定到enter按键')"><br>
        <button @click.left="show('鼠标左键按下')">按下</button>  
    </div>
</template>

<script setup>

    const show = msg => console.log(msg)
    
</script>

<style>
    .demo3{
        text-align: center;
        font-size: 20px;
        color: rgb(24, 233, 73);
        background-color:rgb(121, 168, 222);
    }
</style>