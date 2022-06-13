<template>
  <div>
    <h1>My Counter</h1>
    <p>
      <button @click="decrement" value="減らす">-</button>
      <span>{{ current }}</span>
      <button @click="increment" value="増やす">+</button>
    </p>
  </div>
</template>

<script>
export default {
  name: "MyCounter",
  props: {
    init: []
  },
  data() {
    return {
      current: this.init
    }
  },
  methods: {
    increment() {
      this.current++
    },
    decrement() {
      this.current--
    }
  }
}
</script>

<style scoped>

</style>