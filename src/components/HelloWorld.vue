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
  <div>
    <form>
      <label for="dog">いぬ</label>
      <input type="radio" id="dog" value="いぬ" v-model="pet" />
      <br>
      <label for="cat">ねこ</label>
      <input type="radio" id="cat" value="ねこ" v-model="pet" />
      <br>
      <label for="other">その他</label>
      <input type="radio" id="other" value="その他" v-model="pet" />
    </form>
    <p>私のペットは{{ pet }}です</p>
    </div>
  <div>
    <form>
      <label for="agree" >同意する：</label>
      <input type="checkbox" id="agree" v-model="agree" true-value="yes" false-value="no"/>
    </form>
    <p>回答：{{ agree }}</p>
  </div>

  <div>
    <form>
      <div>お使いのOSは？</div>
      <input type="checkbox" id="windows" value="windows" v-model="os" />
      <label for="windows">Windows</label>
      <br>
      <input type="checkbox" id="mac" value="mac" v-model="os" />
      <label for="mac">Mac</label>
      <br>
      <input type="checkbox" id="linux" value="linux" v-model="os" />
      <label for="linux">Linux</label>
    </form>
    <p>私のOSは{{ os }}です</p>
  </div>
  <div>
    <form>
      <div>お使いのブラウザは？</div>
      <select v-model="browser">
        <option>Chrome</option>
        <option>Firefox</option>
        <option>Safari</option>
        <option>Opera</option>
      </select>
    </form>
    <p>私のブラウザは{{ browser }}です</p>
  </div>
  <div>
    <form>
      <label for="show">表示/非表示</label>
      <input type="checkbox" id="show" v-model="show" />
    </form>
    <div v-if="show">
      <p>表示します</p>
    </div>
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
      pet: 'いぬ',
      agree: true,
      os: ['windows', 'mac', 'linux'],
      browser: "",
      show: true
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
