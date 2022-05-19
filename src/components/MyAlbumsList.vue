<template>
  <div class="container">
    <div class="row row-cols-2 row-cols-md-4">
      <MyAlbum v-for="item in albums" :key="item.index" :albumData="item"/>

    </div>
  </div>
</template>

<script>
import MyAlbum from "./MyAlbum.vue";
import axios from "axios";

export default {
  name: "MyAlbumsList",
  components: {
    MyAlbum,
  },
  data() {
    return {
      albums: [],
    };
  },
  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((resp) => {
        this.albums = resp.data.response;
        console.log(this.albums);
      });
    },
};
</script>

<style lang="scss" scoped>
</style>