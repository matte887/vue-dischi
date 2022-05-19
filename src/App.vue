<template>
  <div id="app">
    <MyHeader />
    <main class="main">
      <MyAlbumsList />
    </main>
  </div>
</template>

<script>
import MyAlbumsList from "./components/MyAlbumsList.vue";
import MyHeader from "./components/MyHeader.vue";

export default {
  name: 'App',
  components: {
    MyAlbumsList,
    MyHeader,
  }
}
</script>

<style lang="scss">
@import "./style/common.scss";

</style>
