<template>
  <input type="text" v-model="keywords" />
  <h2>{{ keywords }}</h2>
</template>

<script>
import { customRef } from "vue";
export default {
  name: "App",
  components: {},
  setup() {
    function myRefs(value, delay) {
      let timer;
      return customRef((track, trigger) => {
        return {
          get() {
            track();
            console.log(`有人获取值了，值为${value}`);
            return value;
          },
          set(newValue) {
            console.log(`有人修改值了，新值为${newValue}`);
            clearTimeout(timer);
            timer = setTimeout(() => {
              value = newValue;
              trigger();
            }, delay);
          },
        };
      });
    }
    let keywords = myRefs("hello", 500);

    return {
      keywords,
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
