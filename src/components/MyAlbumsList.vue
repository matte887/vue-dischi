<template>
  <div class="container">
    <MySelection @selectedGenre="pickSelectedGenre"/>
    <MyLoadingPage v-if="loading" />
    <div v-else class="row row-cols-2 row-cols-md-3 row-cols-lg-4 row-cols-xl-5 g-5 my-5">
      <MyAlbum v-for="item in albums" :key="item.index" :albumData="item" />
    </div>
  </div>
</template>

<script>
import MyLoadingPage from "./MyLoadingPage.vue";
import MySelection from "./MySelection.vue";
import MyAlbum from "./MyAlbum.vue";
import axios from "axios";

export default {
  name: "MyAlbumsList",
  components: {
    MyAlbum,
    MyLoadingPage,
    MySelection,
  },
  data() {
    return {
      albums: [],
      loading: true,
      selectedGenre: ""
    };
  },
  methods: {
    pickSelectedGenre(genreSelection) {
      this.selectedGenre = genreSelection;
      console.log(this.selectedGenre);
    }
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