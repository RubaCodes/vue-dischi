<template>
  <div>
    <!-- utilizzo emit per searchText -->
    <InputText
      class="flex justify-center items-center mx-auto pb-4 gap-4"
      @textToSearch="updateLibrary"
    ></InputText>
    <div class="grid grid-cols-1 md:grid-cols-3 xl:grid-cols-5 gap-x-8 gap-y-4">
      <AlbumCard
        v-for="album in totalfilter"
        :key="album.id"
        :album="album"
      ></AlbumCard>
    </div>
  </div>
</template>

<script>
import AlbumCard from '../blocks/AlbumCard.vue';
import InputText from '../blocks/InputText.vue';
//shared data
import data from '../../shared/data.js';
//axios
import axios from 'axios';

export default {
  components: { AlbumCard, InputText },
  name: 'LibrarySection',
  data() {
    return {
      albums: [],
      artistSearch: '',
      data,
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
  updated() {
    //funzia da updated in poi
    this.getGenres();
  },
  methods: {
    updateLibrary(searchText) {
      this.artistSearch = searchText;
    },

    // ottenimento lista dei generi dagli album
    getGenres() {
      this.data.allGenres = new Set();
      this.data.allGenres.add('All');
      console.log(this.albums.length);
      this.albums.forEach((album) => {
        this.data.allGenres.add(album.genre);
      });
    },
  },
  computed: {
    // filtri distinti pre-unione

    // filterArtist() {
    //   return this.albums.filter((elm) =>
    //     elm.author.toLowerCase().includes(this.artistSearch.toLowerCase())
    //   );
    // },
    // filterGenre() {
    //   if (this.data.genreSelect == 'all') {
    //     return this.albums;
    //   }
    //   return this.albums.filter((elm) =>
    //     elm.genre.toLowerCase().includes(this.data.genreSelect.toLowerCase())
    //   );
    // },

    //filtraggio simultaneo dei generi e degli artisti
    totalfilter() {
      return this.albums.filter(
        (elm) =>
          elm.author.toLowerCase().includes(this.artistSearch.toLowerCase()) &&
          (this.data.genreSelect == 'All'
            ? elm.author.toLowerCase().includes(this.artistSearch.toLowerCase())
            : elm.genre
                .toLowerCase()
                .includes(this.data.genreSelect.toLowerCase()))
      );
    },
  },
};
</script>
