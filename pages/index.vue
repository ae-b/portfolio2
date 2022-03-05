<template>
  <div class="content-area">
    <nav>
      <ul class="content-link">
        <li v-for="content in contents" :key="content.id">
          <nuxt-link :to="`/${content.id}`">
            {{ content.title }}
          </nuxt-link>
        </li>
      </ul>
    </nav>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  async asyncData({ $microcms }) {
    const data = await $microcms.get({
      endpoint: 'portfolio2',
      queries: { fields: 'title,id' },
    });
    console.log(data)
    return data;
  }
}
</script>

<style>

html,body{
  /* TOPページではスクロールさせない */
  /* https://qumeru.com/magazine/278#:~:text=Photo%20byPexels-,CSS%E3%81%A7%E7%94%BB%E9%9D%A2%E3%82%92%E3%82%B9%E3%82%AF%E3%83%AD%E3%83%BC%E3%83%AB%E3%81%95%E3%81%9B%E3%81%AA%E3%81%84%E3%82%88%E3%81%86%E3%81%AB%E3%81%99%E3%82%8B%E6%96%B9%E6%B3%95,-CSS%E3%81%A7%E7%94%BB%E9%9D%A2 */
  overflow: hidden
}

.content-area {
  /* 箱自体の高さ */
  height: 80vh;
  /* ここは画像配置してから細かいところ決める */
  /* https://ics.media/entry/17522/#:~:text=%E3%82%92%E7%A2%BA%E8%AA%8D%E3%81%99%E3%82%8B-,CSS%20Grid%E3%82%92%E4%BD%BF%E3%81%86%E3%81%A82%E8%A1%8C,-CSS%20Grid%E3%83%AC%E3%82%A4%E3%82%A2%E3%82%A6%E3%83%88 */
  display: grid;
  place-items: center;
  /* ここまで */
}

.content-link li a {
  /* 文字関係 */
  font-size: 80px;
  color: rgb(51, 50, 50);
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

.content-area:after {
  /* float leftによる回り込み解除 */
  content: "";
  display: block;
  clear: both;
}


</style>
