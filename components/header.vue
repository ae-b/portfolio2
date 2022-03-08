<template>
  <div class="common-header">
    <header>
        <div class="logo" v-if="isNotIndex">
        <!--
          基本的にimgは使いたいサイズに変えて使用すること。
          ソースはまとめる時に探してください。
         -->
          <a href="/"><img src="~assets/K2.png" alt="top"></a>
          <div class="common-title">{{ title }}</div>
        </div>
    </header>
  </div>
</template>
<script>
export default {
  computed: {
    title() {
      if ('index' == this.$nuxt.$route.name){
        return null
      }
      return this.$nuxt.$route.name
    },
    isNotIndex() {
      return 'index' != this.$nuxt.$route.name
    }
  }
}
</script>

<style>
.logo {
  float: left;
}

.logo:hover {
  /* hoverしたら色を変える */
  opacity: 0.8;
}

img {
  /* img要素の下部に意図しない余白ができないようにする */
  vertical-align: bottom;
}

.common-title {
  /* 文字関係 */
  font-size: 50px;
  font-weight: bold;
  letter-spacing: 2px;
  float: right;
  padding-left: 8px;
}

.common-header {
  height: 80px;
}

</style>
