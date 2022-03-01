<template>
  <div class="father">我是父组件, {{ name }} --- {{ price }}</div>
</template>

<script>
import {
  reactive,
  ref,
  readonly,
  isReactive,
  isReadonly,
  isProxy,
  isRef,
} from "vue";
export default {
  name: "App",
  components: {},
  setup() {
    const car = reactive({
      name: "奔驰",
      price: "40w",
    });

    const sum = ref(0);

    const c = readonly(car);

    console.log(isReactive(car));
    console.log(isRef(sum));
    console.log(isReadonly(c));
    console.log(isProxy(car));

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
  width: 500px;
  height: 500px;
  background: red;
}
</style>
