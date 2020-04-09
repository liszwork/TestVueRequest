// refs.
// https://jp.vuejs.org/v2/cookbook/using-axios-to-consume-apis.html
// [vue-cliでaxiosを使用する(設定から使用方法まで)](https://qiita.com/right1121/items/092ac7ff747e1c47b2b1)
<template>
  <div class="hello">
    <h1>hello!</h1>
    <div>{{ info }}</div>
    <input @click="getReq" type="button" value="click" />
  </div>
</template>

<script>
// qiita api URL
const BASE_URL = 'https://qiita.com/api/v2/';

export default {
  name: 'HelloWorld',
  data () {
    return {
      info: null,
    }
  },
  methods: {
    getReq() {
      this.axios
        // .get('https://qiita.com/api/v2/' + 'items?page=1&per_page=4')
        .get('https://api.coindesk.com/v1/bpi/currentprice.json')
        .then((response) => {
          this.info = response;
        });
    },
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
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
