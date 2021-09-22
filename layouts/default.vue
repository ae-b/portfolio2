<template>
  <div>
    <nav class="header has-shadow is-primary" role="navigation" aria-label="main navigation">
      <a class="navbar-item" href="/">
        <img src="~assets/K2.png" height="28">
      </a>
    </nav>

    <ul class="menu-list">
      <li v-for="(item, key) of items" :key="key">
        <NuxtLink :to="item.to">
          <b-icon :icon="item.icon" /> {{ item.title }}
        </NuxtLink>
      </li>
    </ul>

    <div class="container column is-10">
      <Nuxt />
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      items: [
        {
          // title: 'Home',
          // icon: 'home',
          to: { name: 'index' }
        }
      ]
    }
  }
}
</script>
