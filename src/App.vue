<template>
  <div class="father">
    我是父组件, {{ name }} --- {{ price }}
    <Suspense>
      <template v-slot:default>
        <son></son>
      </template>
      <template v-slot:fallback>
        <h2>加载中。。。</h2>
      </template>
    </Suspense>
  </div>
</template>

<script>
import { provide, reactive, defineAsyncComponent } from "vue";
const son = defineAsyncComponent(() => import("./components/son.vue"));
// import son from "./components/son.vue";
export default {
  name: "App",
  components: {
    son,
  },
  setup() {
    const car = reactive({
      name: "奔驰",
      price: "40w",
    });

    provide("car", car);

    return {
      ...car,
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
.father {
  width: 400px;
  height: 400px;
  background: red;
}
</style>
