<template>
    <div class="demo4">
        <p>{{msg}}</p>
        <p>{{reversedMsg}}</p>
        <p>{{reversedMsg}}</p>
        <button @click="changeMsg">更改</button><br>
        <input type="text" v-model="name">
    </div>
</template>

<script setup>
    import {computed, ref, watch} from 'vue'
    const msg=ref('你好！')

    const reversedMsg = computed(() =>{
        console.log("xixixi")
        return msg.value.split('').reverse().join('')
    })

    const changeMsg =()=>{
        msg.value="世界"
    }

    const name = ref("吴富康")
    watch(name,(newName,oldName)=>
        { console.log(newName,oldName)}
    )

</script>

<style>
.demo4{
        text-align: center;
        font-size: 20px;
        color: rgb(138, 196, 23);
        background-color:rgb(160, 37, 135);
    }
</style>