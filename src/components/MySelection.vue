<template>
  <form class="pt-4">
    <label for="selectGenre" class="me-3">Filtra per genere musicale</label>
    <select
      name="selectGenre"
      id="selectGenre"
      v-model="genreSelection"
      @change="$emit('selectedGenre', genreSelection)"
    >
      <!-- <option disabled value="">Choose a genre</option> -->
      <option value=""></option>
      <option value="rock">Rock</option>
      <option value="pop">Pop</option>
      <option value="jazz">Jazz</option>
      <option value="metal">Metal</option>
    </select>

    <label for="selectArtist" class="me-3">Filtra per artista</label>
    <select
      name="selectArtist"
      id="selectArtist"
      v-model="artistSelection"
      @change="$emit('selectedArtist', artistSelection)"
    >
      <option value=""></option>
      <option value="Bon Jovi">Bon Jovi</option>
    </select>
  </form>
</template>

<script>
export default {
  name: "MySelection",
  data() {
    return {
      genreSelection: "",
      artistSelection: "",
    };
  },
};
</script>

<style lang="scss" scoped>
label {
  color: white;
}
</style>