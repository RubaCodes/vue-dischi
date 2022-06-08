<template>
  <header class="bg-slate-700 p-3 flex justify-between">
    <img class="w-14" src="../assets/img/spotify-logo.png" alt="logo-spotify" />
    <InputSelect></InputSelect>
  </header>
</template>

<script>
import InputSelect from './blocks/InputSelect.vue';

export default {
  components: { InputSelect },
  name: 'BaseHeader',
};
</script>
