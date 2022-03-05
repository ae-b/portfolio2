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
    <div class="logo clearfix">
      <!--
        基本的にimgは使いたいサイズに変えて使用すること。
        ソースはまとめる時に探してください。
       -->
      <a href="/"><img src="~assets/K2.png" alt="top"></a>
    </div>
    <Nuxt />
    <div class="common-footer">
      <!--
        Smallタグとは　https://html-coding.co.jp/annex/dictionary/html/small/
       -->
      <small>portfolio create by ae__b_ photo by sho</small>
    </div>
  </div>
</body>
</template>
<script>
export default {
}
</script>

<style>

body {
  font-family: 'Roboto Condensed', sans-serif;
  min-height:100vh;
  /* https://jajaaan.co.jp/css/css-full-screen/ */

  background-image: url(~assets/tanigawa.jpg);
  background-repeat: no-repeat;
  background-position: center center;
  background-attachment: fixed;
  background-size: cover;
}

.default {
  margin: 16px;
}

.logo {
  float: left;
}

.clearfix::after {
  content: "";
  display: block;
  clear: both;
}

.logo:hover {
  /* hoverしたら色を変える */
  opacity: 0.8;
}

.common-footer {
  /* footerというclass名はうまく動作しない.. */
  text-align: left;
  color: rgb(51, 50, 50);
  /* https://techacademy.jp/magazine/19410 */
  position: absolute;/*←絶対位置*/
  bottom: 16px; /*下に固定*/
}

.common-footer:hover {
  cursor: default;
}

img {
  /* img要素の下部に意図しない余白ができないようにする */
  vertical-align: bottom;
}

</style>
