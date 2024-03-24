<template>
    <!-- <div class="demo2" v-for="(a,b) in user" :key="b">
        值：{{a}}——属性名：{{b}}
    </div> -->

    <!-- <div class="demo2" v-for="a in user" :key="a.id">
        id:{{a.id}}——name:{{a.name}}
    </div> -->

    <!-- <div class="demo2" v-for="(a,b) in user" :key="b">
        索引:{{b}}——值:{{a}}
    </div> -->

    <div class="demo2">
        <p>count的值：{{count}}</p>
        <button @click="addCount($event)">增加</button><br>
        <button @click="addCountN(3,$event)">增加n</button>
    </div>
</template>

<script setup>
    import { reactive, ref } from 'vue';

    const count=ref(1)
    const addCount = event =>{
        count.value++
        if(count.value%2==0){
            event.target.style.border='red dotted'
        }else{
            event.target.style.border='green solid'
        }
    }

    const addCountN = (n,event) =>{
        count.value+=n
        if(count.value%2==0){
            event.target.style.border='red dotted'
        }else{
            event.target.style.border='green solid'
        }
    }
    // const user=reactive({id:"0432220203",name:"伏易卓",sex:"男"})
    // const user=reactive([04
    //     {id:1,name:"12345"},
    //     {id:2,name:"347268"},
    //     {id:3,name:"254327845"},
    // ])
    // const user=reactive(["0432220203","伏易卓","男"])
    
</script>

<style>
    .demo2{
        text-align: center;
        font-size: 20px;
        color: rgb(152, 40, 166);
        background:rgb(92, 92, 135);
    }
</style>