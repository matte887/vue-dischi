<template>
  <div class="container">
    <MySelection @selectedGenre="pickSelectedGenre($event)" @selectedArtist="pickSelectedArtist($event)"/>
    <MyLoadingPage v-if="loading" />
    <div v-else class="row row-cols-2 row-cols-md-3 row-cols-lg-4 row-cols-xl-5 g-5 my-5">
      <MyAlbum v-for="item in filterByGenre" :key="item.index" :albumData="item" />
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
      selected: "",
      // selectedArtist: ""
    };
  },

  methods: {
    pickSelectedGenre(genreSelection) {
      this.selected = genreSelection;
    },
    pickSelectedArtist(genreSelection) {
      this.selected = genreSelection;
    }
  },

  computed: {
    filterByGenre() {
      const filteredByGenre = this.albums.filter((item) => {
        return item.genre.toLowerCase().includes(this.selected.toLowerCase());
      });
      return filteredByGenre;
    },
    filterByArtist() {
      const filteredArtist = this.albums.filter((item) => {
        return item.author.toLowerCase().includes(this.selected.toLowerCase());
      });
      return filteredArtist;
    },
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