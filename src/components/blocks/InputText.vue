<template>
  <form @submit.prevent="$emit('textToSearch', searchText)">
    <input
      class="py-2 px-4 rounded"
      type="text"
      placeholder="Cerca Artista..."
      v-model="searchText"
    />
    <button class="bg-slate-700 text-white py-2 px-4 rounded">Cerca</button>
  </form>
</template>

<script>
export default {
  name: 'InputText',
  data() {
    return {
      searchText: '',
    };
  },
};
</script>
