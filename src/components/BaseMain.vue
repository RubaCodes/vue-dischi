<template>
  <main class="bg-slate-800 h-[full - 74px]">
    <LibrarySection class="w-5/6 md:w-3/4 mx-auto py-12"></LibrarySection>
  </main>
</template>

<script>
import LibrarySection from './sections/LibrarySection.vue';
export default {
  components: { LibrarySection },
  name: 'BaseMain',
};
</script>
