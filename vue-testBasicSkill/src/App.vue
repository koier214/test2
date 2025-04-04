<template>
  <div class="box">
    <h1>原神·塔罗牌</h1>
    <div style="display: flex; width:300px;height:40px;">
      <input type="text" v-model="name"><div class="btn" :class="[ flag ? 'first' : 'second']" @click="add">click me~</div>
    </div>

    <div v-for="(item,index) in list" class="card">
      <div style="display: flex;gap:30px">
        <h1>{{ item.name }}</h1>
        <h3>{{ item.elment }}</h3>
      </div>
      <h2 @click="del(index)">去除~</h2>
      <myDetail @ok="tip" :userName="item.name"></myDetail>
    </div>

  </div>
</template>

<script setup>
import { ref } from 'vue';
import myDetail from './detail.vue'
const name = ref("");
const flag = ref(true);
const list = ref([
  {
    name:"三月七",
    elment:"存护"
  },
  {
    name:"丹恒",
    elment:"巡猎"
  },  {
    name:"胡桃",
    elment:"火·神之眼"
  },
])

function add(){
  flag.value = !flag.value;
  list.value.push({
    name:name.value,
    elment:"暂无"
  })
  name.value = "";
}

function del(index){
  list.value.splice(index,1);
}

function tip(value){
  console.log(value)
}
</script>

<style lang="scss" scoped>
.box{
  .btn{
    width: 100px;
    height: 40px;
    line-height: 40px;
    // background: black;
    color: #fff;
    text-align: center;

  }
  .first{
    background: red;
  }
  .second{
    background: yellow;
  }
  .card{
    width: 320px;
    height: 100px;
    background: bisque;
    color: black;
    margin-bottom:150px ;
  }
}
</style>>
