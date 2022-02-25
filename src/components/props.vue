<template>
  <div class="box1">props组件</div>
  <button @click="emitHello">触发hello事件</button>
</template>

<script>
export default {
  name: 'props',
  components: {
  },
  props: ['msg'],
  emits: ['hello'],
  setup(props, context) {
    // console.log(props)  // Proxy {msg: '传数据过来啦'}
    // console.log(context.attrs); // 若未声明props: ['msg'], 则Proxy {msg: '传数据过来啦', __vInternal: 1}
    // console.log(context.emit); // 触发自定义事件
    console.log(context.slots); // 插槽

    function emitHello() {
      context.emit('hello', 666)

    }

    return {
      emitHello
    }

  }
}
</script>

<style>
.box1 {
  width: 200px;
  height: 200px;
  background: green;
}
</style>
