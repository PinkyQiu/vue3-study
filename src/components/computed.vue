<template>
姓：<input type="text" v-model="person.firstName">
<br />
名：<input type="text" v-model="person.lastName">
<br />
全名：<span>{{person.fullName}}</span>
<br />
全名：<input type="text" v-model="person.fullName">
  
  
</template>

<script>
import { reactive, computed } from 'vue';
export default {
  name: 'App',
  components: {
  },
  setup() {
    const person = reactive({
      firstName: 'z',
      lastName: 's'
    })

    // 没有考虑到计算属性被修改的情况
    // person.fullName = computed(() => {
    //   return person.firstName + '-' + person.lastName;
    // })

    person.fullName = computed({
      get() {
        return person.firstName + '-' + person.lastName;
      },
      set(value) {
        let name = value.split('-');
        person.firstName = name[0];
        person.lastName = name[1];
      }
      
    })
    
    return {
      person
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
