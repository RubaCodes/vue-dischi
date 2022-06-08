<template>
  <div>
    <InputText
      class="flex justify-center items-center mx-auto pb-4 gap-4"
    ></InputText>
    <div class="grid grid-cols-1 md:grid-cols-3 xl:grid-cols-5 gap-x-8 gap-y-4">
      <AlbumCard
        v-for="album in albums"
        :key="album.id"
        :album="album"
      ></AlbumCard>
    </div>
  </div>
</template>

<script>
import AlbumCard from '../blocks/AlbumCard.vue';

import axios from 'axios';
import InputText from '../blocks/InputText.vue';
export default {
  components: { AlbumCard, InputText },
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
      })
      .catch((error) => {
        // handle error
        console.log(error);
      });
  },
};
</script>
