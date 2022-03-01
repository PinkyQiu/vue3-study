<template>
  <div class="son">我是子组件</div>
  <!-- <grandson></grandson> -->
</template>

<script>
// import grandson from "./grandson.vue";
export default {
  name: "App",
  components: {
    // grandson,
  },
  setup() {
    return {};
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
.son {
  width: 300px;
  height: 300px;
  background: green;
}
</style>
