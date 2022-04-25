<template>
  <body>
    <div class="default">
      <!-- コメントはQiita化してほぼ消すこと -->
      <!--
        header・footerといった書き方をすると2つレンダリングされたりしてしまう。
        ・一つ目のdivがnav bar
        ・NuxtにPages配下の内容
        ・二つ目のdivがfooter
        に該当する。
        参考 https://nuxtjs.org/ja/docs/features/nuxt-components#nuxt-%E3%82%B3%E3%83%B3%E3%83%9D%E3%83%BC%E3%83%8D%E3%83%B3%E3%83%88
      -->
      <Header />
      <Nuxt />
      <Footer />
    </div>

  </body>
</template>
<script>

import Header from "@/components/header.vue"; // headerをインポート
import Footer from "@/components/footer.vue"; // footerをインポート

export default {
	components: {
		Header,
		Footer
	},
  computed: {
    title() {
      if ('index' == this.$nuxt.$route.name){
        return null
      }
      return this.$nuxt.$route.name
    }
  }
}
</script>

<style>

.default {
  margin: 16px;
}
</style>
