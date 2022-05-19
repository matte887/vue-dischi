<template>
  <header>
    <img :src="require('../assets/img/spotify.png')" alt="" />
  </header>
</template>

<script>
export default {
  name: "MyHeader",
};
</script>

<style lang="scss" scoped>
header {
  width: 100%;
  height: 80px;
  background-color: #2e3a46;
  color: white;
  display: flex;
  align-items: center;

  img {
      width: auto;
      height: 60px;
      margin-left: 3rem;
  }
}
</style>