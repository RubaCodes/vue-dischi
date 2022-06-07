<template>
  <main class="bg-slate-800">
    <LibrarySection class="w-5/6 md:w-2/3 mx-auto py-8"></LibrarySection>
  </main>
</template>

<script>
import LibrarySection from './sections/LibrarySection.vue';
export default {
  components: { LibrarySection },
  name: 'BaseMain',
};
</script>
