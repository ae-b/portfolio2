<template>
  <div>
    <div class="common-title clearfix">
      {{ "       " + id }}
    </div>
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
  }
}
</script>
<style>

html,body{
  /* TOPページではスクロールさせない */
  overflow: hidden
}

.common-title {
  /* 文字関係 */
  font-size: 50px;
  font-weight: bold;
  letter-spacing: 2px;
}

.clearfix::after {
  content: "";
  display: block;
  clear: both;
}

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
