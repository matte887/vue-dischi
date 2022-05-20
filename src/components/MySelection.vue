<template>
  <div>
    <select name="selectGenre" id="" v-model="genreSelection" @change="$emit('selectedGenre', genreSelection)">
      <!-- <option disabled value="">Choose a genre</option> -->
      <option value=""></option>
      <option value="rock">Rock</option>
      <option value="pop">Pop</option>
      <option value="jazz">Jazz</option>
    </select>
  </div>
</template>

<script>
export default {
  name: "MySelection",
  data() {
      return {
          genreSelection: ""
      }
  },
//   methods: {
//     pickGenre(selezione) {
//       console.log(selezione);
//     },
//   },
};
</script>

<style lang="scss" scoped>
</style>