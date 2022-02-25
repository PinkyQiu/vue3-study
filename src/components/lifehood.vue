<template>
  <button @click="isShow = !isShow">出现/隐藏子组件</button>
  <child v-if="isShow"></child>
</template>

<script>
import { ref } from 'vue';
import child from './components/child.vue';
export default {
  name: 'App',
  components: {
    child
  },
  setup() {
    let isShow = ref(true);
    
    return {
      isShow,
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
