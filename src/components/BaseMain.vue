<template>
  <main class="bg-slate-800">
    <LibrarySection class="w-5/6 md:w-3/5 mx-auto py-14"></LibrarySection>
  </main>
</template>

<script>
import LibrarySection from './sections/LibrarySection.vue';
export default {
  components: { LibrarySection },
  name: 'BaseMain',
};
</script>
