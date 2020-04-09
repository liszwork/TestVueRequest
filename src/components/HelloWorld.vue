<template>
  <div class="hello">
    <article
      v-for="(article, index) in articleList"
      :key="index"
      class="box media">
      <figure class="media-left">
        <p class="image is-64x64">
          <img :src="article.user.profile_image_url">
        </p>
      </figure>
      <div class="media-content">
        <div class="content">
          <p>
            <strong><nuxt-link :to="article.url">{{ article.title}}</nuxt-link></strong> <br>
            {{ article.user.id }}<br>
            <small>Like · {{ article.likes_count }}</small>
          </p>
        </div>
      </div>
    </article>
  </div>
</template>

<script>
// qiita api URL
const BASE_URL = 'https://qiita.com/api/v2/';

export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
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
