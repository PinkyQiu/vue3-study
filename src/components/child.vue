<template>
<h2>当前求和为： {{sum}}</h2>
<button @click="sum++">点我+1</button>
</template>

<script>
import { ref, onBeforeMount, onMounted,  onBeforeUpdate, onUpdated, onUnmounted, onBeforeUnmount } from 'vue';
export default {
  name: 'App',
  components: {
  },
  setup() {
    let sum = ref(0);

    onBeforeMount(() => {
      console.log('---------onBeforeMount--------');
    })

    onMounted(() => {
      console.log('---------onMounted--------');
    })

    onBeforeUpdate(() => {
      console.log('---------onBeforeUpdate--------');
    })

    onUpdated(() => {
      console.log('---------onUpdated--------');
    })

    onBeforeUnmount(() => {
      console.log('---------onBeforeUnmount--------');
    })

    onUnmounted(() => {
      console.log('---------onUnmounted--------');
    })
    
    return {
      sum,
    }
  },
  beforeCreate() {
    console.log('---------beforeCreate--------');
  },
  created() {
    console.log('---------created--------');
  },
  beforeMount() {
    console.log('---------beforeMount--------');
  },
  mounted() {
    console.log('---------mounted--------');
  },
  beforeUpdate() {
    console.log('---------beforeUpdate--------');
  },
  updated() {
    console.log('---------updated--------');
  },
  beforeUnmount() {
    console.log('---------beforeUnmount--------');
  },
  unmounted() {
    console.log('---------unmounted--------');
  },

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
