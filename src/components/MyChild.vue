<template>
  <div>
    <p>子：{{ childMessage }}</p>
  </div>

</template>

<script>
export default {
  name: "MyChild",
  data() {
    return {
      childMessage: ''
    }
  },
  //マウント時に親のmessageを設定
  mounted() {
    this.$parent.parentMessage = "子からのメッセージ"
  },

}
</script>

<style scoped>

</style>