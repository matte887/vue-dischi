<template>
  <div class="container">
      <div class="row row-cols-2 row-cols-md-4">
          <MyAlbum />
          <MyAlbum />
          <MyAlbum />
          <MyAlbum />
          <MyAlbum />
          <MyAlbum />
          <MyAlbum />
          <MyAlbum />
      </div>
  </div>
</template>

<script>
import MyAlbum from "./MyAlbum.vue";

export default {
  name: "MyAlbumsList",
  components: {
      MyAlbum,
  },
  created: {
      
  }
};
</script>

<style lang="scss" scoped>

</style>