<template>
  <div class="grid grid-cols-5 mx-auto">
    <AlbumCard v-for="i in 10" :key="i"></AlbumCard>
  </div>
</template>

<script>
import AlbumCard from '../blocks/AlbumCard.vue';
export default {
  components: { AlbumCard },
  name: 'LibrarySection',
};
</script>
