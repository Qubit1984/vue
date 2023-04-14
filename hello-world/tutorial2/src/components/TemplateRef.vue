<template>
  <div>
    <input type="text" ref="inputRef" />
    <Postlist ref="postlistsRef" />
  </div>
</template>

<script>
import Postlist from './Postlist.vue';
export default {
  name: 'TemplateRef',
  components: {
    Postlist,
  },
  mounted() {
    console.log(this.$refs.postListRef);
    this.$refs.inputRef.focus();
  },
};
</script>

<style scoped>
</style>