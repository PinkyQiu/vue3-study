<template>
  <h2>用户信息：</h2>
  <div>姓名：{{ name }}</div>
  <div>年龄：{{ age }}</div>
  <div>工作类型：{{ job.type }}</div>
  <div>薪资： {{ job.salary }}</div>
  <br />
  <br />
  <button @click="sayHello">按钮</button>
  <br />
  <br />
  <button @click="changeInfo">更新用户信息</button>
</template>

<script>
import { ref } from "vue";
export default {
  name: "App",
  components: {},
  setup() {
    let name = ref("zs");
    let age = ref(18);
    const job = ref({
      type: "前端工程师",
      salary: "20k",
    });

    function sayHello() {
      alert(`我叫${name}, 今年${age}`);
    }

    function changeInfo() {
      name.value = "ls";
      age.value = 20;

      job.value.type = "ui设计师";
      job.value.salary = "22k";
    }

    return {
      name,
      age,
      job,
      sayHello,
      changeInfo,
    };
  },
};
</script>

<style>
</style>
