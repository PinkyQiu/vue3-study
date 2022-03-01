<template>
  <button @click="isShow = true">打开弹窗</button>
  <teleport to="body" v-if="isShow">
    <div class="dialog">
      <h2>弹窗标题</h2>
      <button @click="isShow = false">点击关闭弹窗</button>
    </div>
  </teleport>
</template>

<script>
import { ref } from "vue";
export default {
  name: "App",
  components: {},
  setup() {
    let isShow = ref(false);
    return {
      isShow,
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
.dialog {
  width: 100px;
  height: 100px;
  background: blue;
}
</style>
