<template>
  <div class="common-footer">
    <!--
      Smallタグとは　https://html-coding.co.jp/annex/dictionary/html/small/
     -->
    <small>portfolio create by ae__b_ photo by sho</small>
  </div>
</template>

<style>
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
</style>
