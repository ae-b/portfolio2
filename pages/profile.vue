<template>
  <div id="wrap">
    <div class="">
      <span v-html="body"></span>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  async asyncData() {
    const { data } = await axios.get(
      process.env.SERVICE_DOMAIN ,
      {
        headers: { 'X-API-KEY': process.env.API_KEY }
      }
    )
    let body
    data.contents.forEach(c => {
      if (c.id == 'profile') body = { body: c.body }
    })
    return body
  }
}
</script>

<style>
div {
  height: 80vh;
}

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
