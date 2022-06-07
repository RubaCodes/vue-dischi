<template>
  <div class="grid grid-cols-5 mx-auto gap-4">
    <AlbumCard
      v-for="album in albums"
      :key="album.id"
      :album="album"
    ></AlbumCard>
  </div>
</template>

<script>
import AlbumCard from '../blocks/AlbumCard.vue';
import axios from 'axios';
export default {
  components: { AlbumCard },
  name: 'LibrarySection',
  data() {
    return {
      albums: [],
    };
  },
  created() {
    axios
      .get('https://flynn.boolean.careers/exercises/api/array/music')
      .then((response) => {
        // handle success
        this.albums = response.data.response;
        console.log(this.albums);
      })
      .catch((error) => {
        // handle error
        console.log(error);
      });
  },
};
</script>
