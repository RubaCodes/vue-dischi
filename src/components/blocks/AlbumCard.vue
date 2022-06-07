<template>
  <div class="card text-center p-5 bg-slate-700">
    <img class="w-full" :src="album.poster" :alt="album.title" />
    <h2 class="text-white uppercase text-2xl font-bold pt-5">
      {{ album.title }}
    </h2>
    <div class="text-slate-400 capitalize text-xl pt-3">{{ album.author }}</div>
    <div class="text-slate-400 text-xl">{{ album.year }}</div>
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
