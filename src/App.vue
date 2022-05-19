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

</style>
