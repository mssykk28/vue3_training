<template>
  <div>
    <button type="button" v-on:click="onClick">{{ step }}</button>
  </div>
</template>

<script>
export default {
  name: "MyCounter2",
  props: {
    step: Number
  },
  emits: {
    plusMinus: {
      type: Number,
      default: 1
    }
  },
  data() {

  },
  methods: {
    onClick() {
      this.$emit("plusMinus", Number(this.step))
    }
  }
}
</script>

<style scoped>

</style>