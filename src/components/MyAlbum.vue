<template>
  <div class="col">
    <div class="my-card text-center py-4">
      <img
        :src="albumData.poster"
        alt=""
      />
      <h3 class="py-3 text-uppercase">{{albumData.title}}</h3>
      <span class="text-secondary">{{albumData.author}}</span>
      <span class="text-secondary">{{albumData.year}}</span>
    </div>

  </div>
</template>

<script>
export default {
    name: "MyAlbum",
    props: {
        albumData: Object
    }
};
</script>

<style lang="scss" scoped>
.my-card {
  background-color: #2e3a46;
  color: white;
  padding: 1rem;
  height: 100%;

  span {
    display: block;
  }
}
</style>