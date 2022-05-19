<template>
  <div id="app">
    <main class="main">
      <MyAlbumsList />
    </main>
  </div>
</template>

<script>
import MyAlbumsList from "./components/MyAlbumsList.vue"

export default {
  name: 'App',
  components: {
    MyAlbumsList,
  }
}
</script>

<style lang="scss">
@import "./style/common.scss";

main {
  width: 100%;
  height: 100vh;
  background-color: #1e2d3b;
}

</style>
