<template>
  <div class="hello">
    <h1>{{ msg }}</h1>

    <button @click="onClick">クリック</button>
    <p>{{ message }}</p>
  </div>
  <div>
    <img v-bind:src="path" alt="画像"
    @mouseenter="onmouseenter" @mouseleave="onmouseleave" />
  </div>
  <div>
    <form>
      <label for="name">名前</label>
      <input type="text" id="name" v-model="myName" />
    </form>
    <p>こんにちは、{{ myName }}さん</p>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
    return {
      message: '',
      path: 'https://www.web-deli.com/image/linkbanner_l.gif',
      myName: '匿名',
    }
  },
  methods: {
    //  クリック時に現在日時を取得
    onClick() {
      this.message = new Date().toLocaleString();
    },
    // 画像にマウスポインターが乗った時
    onmouseenter() {
      this.path = 'https://www.web-deli.com/image/home_chara.gif';
    },
    // 画像からマウスポインターが外れた時
    onmouseleave() {
      this.path = 'https://www.web-deli.com/image/linkbanner_l.gif';
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
