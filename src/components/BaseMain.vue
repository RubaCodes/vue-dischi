<template>
  <main class="h-full bg-slate-800">
    <LibrarySection></LibrarySection>
  </main>
</template>

<script>
import LibrarySection from './sections/LibrarySection.vue';
export default {
  components: { LibrarySection },
  name: 'BaseMain',
};
</script>
