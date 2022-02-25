<template>
  <h2>当前求和为： {{sum}}</h2>
  <button @click="sum++">点我+1</button>
  <hr>
  <h2>当前信息： {{msg}}</h2>
  <button @click="msg+='!'">点我+1</button>
  <hr>
  <h2>用户信息：</h2>
  <br />
  <div v-show="person.name">姓名：{{person.name}}</div>
  <br />
  <div>年龄：{{person.age}}</div>
  <br />
  <button @click="person.name+='!'">修改姓名</button>
  <button @click="person.age++">修改年龄</button>
  <hr>
  <div>工作类型：{{person.job.type}}</div>
  <br />
  <div>薪资： {{person.job.salary}}</div>
  <br />
  <button @click="person.job.salary+=1">修改薪资</button>
</template>

<script>
import { reactive, ref, watch, watchEffect} from 'vue';
export default {
  name: 'App',
  components: {
  },
  setup() {
    let sum = ref(0);
    let msg = ref('你好啊');
    let person = reactive({
      name: 'zs',
      age: 20,
      job: {
        type: '前端工程师',
        salary: 12
      }
    })
    // 监听基础类型，会返回newValue, oldValue
    // watch(sum, (newValue, oldValue) => {
    //   console.log(newValue, oldValue)
    // }, { immediate: true, deep: true})

    // watch(msg, (newValue, oldValue) => {
    //   console.log(newValue, oldValue)
    // })

    // watch([msg, sum], (newValue, oldValue) => {
    //   console.log(newValue, oldValue)
    // }, { immediate: true, deep: true})

    // 问题1、oldValue和newValue一样，无法获取oldValue
    // watch(person, (newValue, oldValue) => {
    //   console.log('person数据修改了', newValue, oldValue);
    // })

    // watch(() => person.name, (newValue, oldValue) => {
    //   console.log('person数据修改了', newValue, oldValue);
    // })

    // watch([() => person.name, () => person.age], (newValue, oldValue) => {
    //   console.log('person数据修改了', newValue, oldValue);
    // })

    // watch(person.job, (newValue, oldValue) => {
    //   console.log('person数据修改了', newValue, oldValue);
    // }, {
    //   deep: true,
    // })

    // watchEffect(() => {
    //   const a = person.name; // 用到了哪个属性，才能监听到
    //   console.log('修改了')
    // })
    
    return {
      sum,
      msg,
      person
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
