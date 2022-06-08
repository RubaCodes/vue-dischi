<template>
  <select v-model="data.genreSelect" class="px-4 text-center">
    <option
      v-for="(genres, index) in data.allGenres"
      :value="genres"
      :key="index"
    >
      {{ genres }}
    </option>
  </select>
</template>

<script>
import data from '../../shared/data';
export default {
  name: 'InputSelect',
  data() {
    return {
      data,
    };
  },
};
</script>
