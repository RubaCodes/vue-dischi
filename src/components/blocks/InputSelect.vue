<template>
  <select v-model="data.genreSelect" class="px-4 text-center">
    <option value="all" selected>All</option>
    <option value="pop">pop</option>
    <option value="rock">rock</option>
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
