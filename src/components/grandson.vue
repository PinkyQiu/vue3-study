<template>
  <div class="grandson">
    我是孙子组件: {{ car.name }} ----- {{ car.price }}
    <ialog></ialog>
  </div>
</template>

<script>
import { inject } from "vue";
import ialog from "./dialog.vue";
export default {
  name: "App",
  components: {
    ialog,
  },
  setup() {
    let car = inject("car");
    return {
      car,
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
.grandson {
  width: 200px;
  height: 200px;
  background: orange;
}
</style>
