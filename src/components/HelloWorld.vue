<template>
  <div class="hello">
    <h1>{{ msg }}</h1>

    <button @click="onClick">クリック</button>
    <p>{{ message }}</p>
  </div>
  <div>
    <img v-bind:src="path" alt="画像"
         @mouseenter="onmouseenter" @mouseleave="onmouseleave"/>
  </div>
  <div>
    <form>
      <label for="name">名前</label>
      <input type="text" id="name" v-model="myName"/>
    </form>
    <p>こんにちは、{{ myName }}さん</p>
  </div>
  <div>
    <form>
      <label for="dog">いぬ</label>
      <input type="radio" id="dog" value="いぬ" v-model="pet"/>
      <br>
      <label for="cat">ねこ</label>
      <input type="radio" id="cat" value="ねこ" v-model="pet"/>
      <br>
      <label for="other">その他</label>
      <input type="radio" id="other" value="その他" v-model="pet"/>
    </form>
    <p>私のペットは{{ pet }}です</p>
  </div>
  <div>
    <form>
      <label for="agree">同意する：</label>
      <input type="checkbox" id="agree" v-model="agree" true-value="yes" false-value="no"/>
    </form>
    <p>回答：{{ agree }}</p>
  </div>

  <div>
    <form>
      <div>お使いのOSは？</div>
      <input type="checkbox" id="windows" value="windows" v-model="os"/>
      <label for="windows">Windows</label>
      <br>
      <input type="checkbox" id="mac" value="mac" v-model="os"/>
      <label for="mac">Mac</label>
      <br>
      <input type="checkbox" id="linux" value="linux" v-model="os"/>
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
      <input type="checkbox" id="show" v-model="show"/>
    </form>
    <div v-if="show">
      <p>表示します</p>
    </div>
    <div v-else>
      <p>非表示にします</p>
    </div>

    <div>
      <form>
        <label for="holiday">祝日：</label><br>
        <select id="holiday" v-model="holiday">
          <option value="">祝日を選択してください</option>
          <option value="1">元日</option>
          <option value="2">成人の日</option>
          <option value="3">建国記念の日</option>
          <option value="4">春分の日</option>
          <option value="5">憲法記念日</option>
          <option value="6">みどりの日</option>
          <option value="7">こどもの日</option>
          <option value="8">海の日</option>
          <option value="9">敬老の日</option>
          <option value="10">秋分の日</option>
          <option value="11">体育の日</option>
          <option value="12">文化の日</option>
          <option value="13">勤労感謝の日</option>
          <option value="14">天皇誕生日</option>
        </select>
      </form>
      <div v-if="holiday==='1'">
        <p>年始</p>
      </div>
      <div v-else-if="holiday==='2'">
        <p>成人の日</p>
      </div>
      <div v-else-if="holiday==='3'">
        <p>建国記念の日</p>
      </div>
      <div v-else-if="holiday==='4'">
        <p>春分の日</p>
      </div>
      <div v-else-if="holiday==='5'">
        <p>憲法記念日</p>
      </div>
      <div v-else-if="holiday==='6'">
        <p>みどりの日</p>
      </div>
      <div v-else-if="holiday==='7'">
        <p>こどもの日</p>
      </div>
      <div v-else-if="holiday==='8'">
        <p>海の日</p>
      </div>
      <div v-else-if="holiday==='9'">
        <p>敬老の日</p>
      </div>
      <div v-else-if="holiday==='10'">
        <p>秋分の日</p>
      </div>
      <div v-else-if="holiday==='11'">
        <p>体育の日</p>
      </div>
      <div v-else-if="holiday==='12'">
        <p>文化の日</p>
      </div>
      <div v-else-if="holiday==='13'">
        <p>勤労感謝の日</p>
      </div>
      <div v-else-if="holiday==='14'">
        <p>天皇誕生日</p>
      </div>
      <div v-else>何も選択されていません。</div>
    </div>

    <div>
      <table>
        <th>No</th>
        <th>ISBN</th>
        <th>書籍名</th>
        <th>価格</th>
        <tr v-for="(book,i) in books" :key="book.index">
          <td>{{ i + 1 }}</td>
          <td>{{ book.isbn }}</td>
          <td>{{ book.title }}</td>
          <td>{{ book.price }}</td>
        </tr>
      </table>
    </div>

    <div>
      <ul v-for="(value,key) in book" :key="key">
        <li>{{ key }}: {{ value }}</li>
      </ul>
    </div>

    <div>
      <ul>
        <li v-for="[key,value] in map" :key="key">
          {{ key }}:{{ value }}
        </li>
      </ul>
    </div>

    <div>
      <ul>
        <li v-for="[key] in map" :key="key">
          {{ key }}
        </li>
      </ul>
    </div>

    <div>
      <ul>
        <li v-for="[, value] in map" :key="value">
          {{ value }}
        </li>
      </ul>
    </div>

    <div>
      <span v-for="i in 5" :key="i">{{ i * 2 }}</span>
    </div>

    <div>
      <table>
        <th>No</th>
        <th>ISBN</th>
        <th>書籍名</th>
        <th>価格</th>
        <tr v-for="(book,i) in expensiveBooks" :key="book.index">
          <td>{{ i + 1 }}</td>
          <td>{{ book.isbn }}</td>
          <td>{{ book.title }}</td>
          <td>{{ book.price }}</td>
        </tr>
      </table>
    </div>

    <div>
      <table>
        <th>No</th>
        <th>ISBN</th>
        <th>書籍名</th>
        <th>価格</th>
        <tr v-for="(book,i) in books" :key="book.index">
          <template v-if="book.price > 3000">
            <td>{{ i + 1 }}</td>
            <td>{{ book.isbn }}</td>
            <td>{{ book.title }}</td>
            <td>{{ book.price }}</td>
          </template>
        </tr>
      </table>
    </div>

    <div>
      <form>
        <input type="button" value="変更" @click="change">
      </form>
    </div>
    <ul>
      <li v-for="item in list" :key="item">{{ item }}</li>
    </ul>

    <div>
      <form>
        <label for="memo">メモ：</label>
        <input type="text" id="memo" v-bind="attrs">
      </form>
    </div>

    <div>
      <select v-model="attr">
        <option value="height">高さ</option>
        <option value="width">幅</option>
      </select>:
      <input type="text" v-model="size"><br>
      <img src="https://wings.msn.to/image/wings.jpg" v-bind:[attr]="size" alt="フリー画像"/>
    </div>

    <!--  htmlの埋め込み  -->
    <div>
      <p>{{ message_html }}</p>
      <!-- 以下のようにするとhtmlタグの中身表示     -->
      <p v-html="message_html"></p>
    </div>

    <div>
      <form>
        <label for="name">氏名：</label>
        <input type="text" id="name" v-model="name">
      </form>
      <!-- 初回だけしか反映されない -->
      <div v-once>初めまして、{{ name }} さん。</div>
      <div>初めまして、{{ name }} さん。</div>
    </div>

    <div>
      <div v-bind:style="{backgroundColor:'Aqua',fontSize:'1.5em'}">
        みなさん、こんにちは！
      </div>
      <div v-bind:style="{'background-color':'Red','font-size':'1.5em'}">
        みなさん、こんにちは！その２
      </div>
    </div>

    <div>
      <div v-bind:style="[color, size]">
        みなさん、こんにちは！（複数スタイル）
      </div>
    </div>

    <div class="small" v-bind:class="{cl, frame:isChange}">
      みなさん、こんにちは！その3
    </div>

    <div class="small cl frame">
      みなさん、こんにちは！その4
    </div>

    <!-- preventは、イベント規定の動作をキャンセル  -->
    <div id="main" v-on:contextmenu.prevent>
      この領域では、コンテキストメニューがs表示されません。
    </div>

    <div>
      <form method="POST" v-on:submit="onsubmit">
        <label for="email">メールアドレス：</label>
        <input type="email" id="email" name="email"/>
        <input type="submit" value="送信"/>
      </form>
    </div>
    <div>
      <input type="button" value="結果表示" v-on:click.once="onClickResult"/>
      <p>今日の運勢は{{ result }}点です。</p>
    </div>

    <div>
      <form>
        <label for="name">氏名：</label>
        <input type="text" id="name" v-on:keyup.esc="clear" v-model="name">
      </form>
    </div>

    <div>
      <form>
        <label for="name">氏名：</label>
        <input type="text" id="name" v-on:keyup.ctrl.q="help" v-model="name">
      </form>
    </div>

    <div>
      <div v-on:click.left="onLeftClick" v-on:click.right.prevent="onRightClick">
        ボタンの右クリックでコンテキストメニューを表示します。
      </div>
      <!--  コンテキストメニューの定義    -->
      <ul class="cxt" v-bind:style="pos" v-show="show_mouse_btn">
        <li><a href="">ヘルプ</a></li>
        <li><a href="">質問掲示板</a></li>
        <li><a href="">よくある指紋一覧</a></li>
      </ul>

      <div>
        <MyCounter init="0"/>
      </div>

      <div>
        <MyHello title="input" my-attr="my-attr" class="sub"></MyHello>
      </div>


    </div>
  </div>

</template>

<script>
import MyCounter from './MyCounter.vue'
import MyHello from './MyHello.vue'

export default {
  components: {
    MyCounter,
    MyHello
  },
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
      show: true,
      holiday: "",
      books: [
        {isbn: '978-4-7741-8411-1', title: '改訂新版Vue本格入門〜Vue3対応〜', price: 2980},
        {isbn: '978-4-7980-4853-6', title: 'はじめてのVue開発', price: 3200},
        {isbn: '978-4-7981-3547-2', title: 'はじめての開発', price: 3480}
      ],
      book: {
        isbn: '978-4-7741-8411-1',
        title: '改訂新版Vue本格入門〜Vue3対応〜',
        price: 2980
      },
      map: new Map([
        ['PHP', 'value1'],
        ['Python', 'value2'],
        ['Java', 'value3']
      ]),
      list: ["赤パジャマ", "白パジャマ", "青パジャマ"],
      attrs: {
        size: '20',
        maxlength: '14',
        required: true,
      },
      attr: "height",
      size: "100",
      message_html: `<p>こんにちは</p>'
      <img src="https://www.web-deli.com/image/linkbanner_l.gif" alt="ロゴ"/>`,
      name: '匿名',
      color: {
        backgroundColor: 'Pink',
        fontSize: '1.5em'
      },
      cl: true,
      isChange: false,
      result: '-',
      pos: {
        left: 0,
        top: 0
      },
      show_mouse_btn: false
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
    },
    change() {
      this.list[1] = '茶パジャマ';
      // 配列の先頭要素を削除
      this.list.shift();
    },
    onsubmit(e) {
      if (!confirm('送信しますか？')) {
        e.preventDefault();
        return;
      }
    },
    onClickResult() {
      this.result = Math.floor(Math.random() * 100) + 1;
    },
    clear() {
      this.name = '';
    },
    help() {
      window.alert('氏名（漢字）を入力してください');
    },
    onLeftClick() {
      //左クリックでメニューを非表示
      this.show_mouse_btn = false;
    },
    onRightClick(e) {
      this.pos = {
        left: e.pageY + 'px',
        top: e.pageX + 'px'
      }
      //右クリックでメニューを表示
      this.show_mouse_btn = true;
    }
  },
  computed: {
    expensiveBooks() {
      return this.books.filter(book => book.price >= 3000);
    },
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
