<template>
  <h2>用户信息：</h2>
  <br />
  <div v-show="person.name">姓名：{{person.name}}</div>
  <br />
  <div>年龄：{{person.age}}</div>
  <br />
  <div v-show="person.sex">性别：{{person.sex}}</div>
  <br />
  <div>工作类型：{{person.job.type}}</div>
  <br />
  <div>薪资： {{person.job.salary}}</div>
  <br />
  <div>兴趣： {{person.hobby[0]}}</div>
  <br />
  <br />
  <button @click="changeInfo">更新用户信息</button>
  <br />
  <br />
  <button @click="addInfo">新增用户信息</button>
  <br />
  <br />
  <button @click="deleteInfo">删除用户信息</button>
  
</template>

<script>
import { reactive, ref } from 'vue';
export default {
  name: 'App',
  components: {
  },
  setup() {
    const person = reactive({
      name: 'zs',
      age: 20,
      job: {
        type: '前端工程师',
        salary: '10k',
        a: {
          b: 'bbb',
        }
      },
      hobby: ['学习', '唱歌', '跳舞']
    })

    function changeInfo() {
      person.name = 'ls';
      person.age = 20;

      person.job.type = 'ui设计师';
      person.job.salary = '22k';
      person.hobby[0] = '睡觉';
    }

    function addInfo() {
      person.sex = '男';
    }

    function deleteInfo() {
      delete person.name;
    }

    return {
      person,
      changeInfo,
      deleteInfo,
      addInfo,
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
