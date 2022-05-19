<template>
  <div class="container">
    <MyLoadingPage v-if="loading" />
    <div v-else class="row row-cols-2 row-cols-md-5 g-5 my-5">
      <MyAlbum v-for="item in albums" :key="item.index" :albumData="item" />
    </div>
  </div>
</template>

<script>
import MyLoadingPage from "./MyLoadingPage.vue";
import MyAlbum from "./MyAlbum.vue";
import axios from "axios";

export default {
  name: "MyAlbumsList",
  components: {
    MyAlbum,
    MyLoadingPage,
  },
  data() {
    return {
      albums: [],
      loading: true
    };
  },
  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((resp) => {
        this.albums = resp.data.response;
        this.loading = false;
      });
  },
};
</script>

<style lang="scss" scoped>
</style>