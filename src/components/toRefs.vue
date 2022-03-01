<template>
  <h2>当前点击鼠标坐标为：x: {{ point.x }}, y: {{ point.y }}</h2>
  <hr />
  <div>姓名：{{ name }}</div>
  <div>年龄：{{ age }}</div>
  <div>工作类型：{{ type }}</div>
  <div>薪资： {{ salary }}</div>
  <br />
  <br />
  <button @click="name += '~'">修改名字</button>
  <br />
  <button @click="age += 1">修改年龄</button>
  <br />
  <button @click="salary += 1">修改薪资</button>
</template>

<script>
import { ref, reactive, toRef, toRefs } from "vue";
import usePoint from "./hooks/usePoint";
export default {
  name: "App",
  components: {},
  setup() {
    let isShow = ref(true);
    const point = usePoint();
    const person = reactive({
      name: "zs",
      age: 18,
      job: {
        type: "前端工程师",
        salary: 18,
      },
    });

    return {
      isShow,
      point,
      // name: toRef(person, "name"),
      // age: toRef(person, "age"),
      // type: toRef(person.job, "type"),
      // salary: toRef(person.job, "salary"),
      ...toRefs(person),
      salary: toRef(person.job, "salary"),
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
