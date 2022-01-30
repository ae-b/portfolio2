<template>
<body>
  <div>
    <TheHeader>
      <NuxtLink to="/"><img src="~assets/K2.png" alt="top" class="logo"></NuxtLink>
    </TheHeader>
    <Nuxt />
    <footer>
      <small>portfolio create by ae__b_ photo by sho</small>
    </footer>
  </div>
</body>
</template>
<script>
export default {
}
</script>
<style>

body {
    height: 100vh;
    background-image: url(~assets/tanigawa.jpg);
    background-repeat: no-repeat;
    background-position: center center;
    background-attachment: fixed;
    background-size: cover;
}

div {
  font-family: 'Roboto Condensed', sans-serif;
}

.logo {
  height: 40px;
  margin: 8px;
}

.logo:hover {
  opacity: 0.8;
}

footer {
  text-align: left;
  color: rgb(51, 50, 50);
  padding: 20px 8px;
}

footer small {
  font-size: 12px;
}

footer:hover {
  cursor: default;
}

img {
  /* img要素の下部に意図しない余白ができないようにする */
  vertical-align: bottom;
}

</style>
