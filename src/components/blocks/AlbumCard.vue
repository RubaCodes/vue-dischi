<template>
  <div class="card text-center p-3 bg-slate-600">
    <img class="w-full" :src="album.poster" :alt="album.title" />
    <h2 class="text-white uppercase">{{ album.title }}</h2>
    <div class="text-slate-500 capitalize">{{ album.artist }}</div>
    <div class="text-slate-500">{{ album.year }}</div>
  </div>
</template>

<script>
export default {
  name: 'AlbumCard',
  props: {
    album: Object,
  },
};
</script>
