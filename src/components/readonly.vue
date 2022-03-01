<template>
  <h2>当前点击鼠标坐标为：x: {{ point.x }}, y: {{ point.y }}</h2>
  <hr />
  <div>姓名：{{ person.name }}</div>
  <div>年龄：{{ person.age }}</div>
  <div>工作类型：{{ person.job.type }}</div>
  <div>薪资： {{ person.job.salary }}</div>
  <br />
  <br />
  <button @click="person.name += '~'">修改名字</button>
  <br />
  <button @click="person.age += 1">修改年龄</button>
  <br />
  <button @click="person.job.salary += 1">修改薪资</button>
</template>

<script>
import { ref, reactive, shallowReadonly } from "vue";
import usePoint from "./hooks/usePoint";
export default {
  name: "App",
  components: {},
  setup() {
    let isShow = ref(true);
    const point = usePoint();
    let person = reactive({
      name: "zs",
      age: 18,
      job: {
        type: "前端工程师",
        salary: 18,
      },
    });
    // person = readonly(person);
    person = shallowReadonly(person);
    return {
      isShow,
      point,
      person,
    };
  },
};
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
