<template>
  <div class="card text-center p-5 bg-slate-600">
    <img class="w-full" :src="album.poster" :alt="album.title" />
    <h2 class="text-white uppercase text-xl font-bold pt-4">
      {{ album.title }}
    </h2>
    <div class="text-slate-400 capitalize">{{ album.author }}</div>
    <div class="text-slate-400">{{ album.year }}</div>
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
