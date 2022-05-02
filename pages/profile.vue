<template>
  <div>
    <div class="body-text">
      <span v-html="body"></span>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  // 各ページで必要なものだけ取得する
  async asyncData({ $microcms }) {
    const data = await $microcms.get({
      endpoint: 'portfolio2',
      contentId: 'profile',
    });
    return data;
  },
  head: {
    bodyAttrs: {
      class: 'body-profile'
    }
  }
}
</script>
<style>

html,body{
  /* TOPページではスクロールさせない */
  overflow: hidden
}

.body-profile {
  width: 50%;
  height: 100%;
  margin: 0px 0px 0px 50%;
}

.body-profile::before {
  content: '';
  width: 50%;
  height: 100%;
  background-image: url(~assets/profile.jpg);
  background-position: center center;
  background-repeat: no-repeat;
  background-size: cover;
  background-attachment: fixed;
  position: absolute;
  top: 0px;
  left: 0px;
}
/*
.body-profile::after {
  content: '';
  background-color: rgba(0, 0, 0, 0.5);
} */

.body-text {
  font-size: 30px;
}

</style>

<!--


.content-area {
  display: flex;
  align-items: center;
  flex-direction: column;
}

.content-link li {
  /* 横並びにする */
  float: left;
  /* 余白 */
  margin: 0 100px;
  /* アンダーラインを引く */
  border-bottom: 5px solid rgb(51, 50, 50);
  padding-bottom: 1px;
  display: inline;
  line-height: 1.5;
}

a {
  /* 文字関係 */
  font-size: 80px;
  color: rgb(51, 50, 50);
}

.content-area:after {
  /* float leftによる回り込み解除 */
  content: "";
  display: block;
  clear: both;
}
</style>
-->
