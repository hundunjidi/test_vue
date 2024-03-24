<template>
    <div class="demo2">
        <input v-model="info">
        我的姓名：{{ info }}<br>
        <input v-model.number="n1">+<input v-model.number="n2">={{ n1+n2 }}
        <p>所修功法：</p>
        <p v-show="type==='a'">逆升三重</p>
        <p v-show="type==='b'">雷法</p>
        <p v-show="type==='c'">丹噬</p>
        <button @click="type='a'">切换三一门</button>
        <button @click="type='b'">切换龙虎山</button>
        <button @click="type='c'">切换唐门</button>
    </div>
</template>

<script setup>
    import { ref } from 'vue';

    const info=ref('0432220227吴富康')
    const n1=ref() 
    const n2=ref()
    const type=ref('b')
</script>

<style>
    .demo2{
        text-align: center;
        font-size: 20px;
        color: rgb(152, 40, 166);
        background:rgb(92, 92, 135);
    }
</style>