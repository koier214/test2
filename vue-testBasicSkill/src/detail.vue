<template>
    <div class="box">
        <h1>姓名:{{ props.userName }}</h1> 
        <h3 @click="send">查看详细信息</h3>
    </div>
</template>

<script setup>
import { defineProps, defineEmits } from 'vue';
const props = defineProps(['userName']);
// const props = defineProps([{ userName: { type:String,required:true } }]);

const emit = defineEmits(['ok'])

function send(){

    emit('ok','快回星穹列车！')
}
</script>