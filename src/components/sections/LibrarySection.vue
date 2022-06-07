<template>
  <div class="grid grid-cols-5 mx-auto gap-4">
    <AlbumCard v-for="i in 10" :key="i"></AlbumCard>
  </div>
</template>

<script>
import AlbumCard from '../blocks/AlbumCard.vue';
import axios from 'axios';
export default {
  components: { AlbumCard },
  name: 'LibrarySection',
};
</script>
