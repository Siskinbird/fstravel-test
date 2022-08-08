<template>

  <div class="content">
    <Author />
    <CardOne />
  </div>
</template>

<script>

import Author from '@/components/Author.vue'
import CardOne from '@/components/CardOne.vue'

export default {
  name: 'Content',
  components: {
    Author,
    CardOne
  }
}
</script>


<style scoped lang="scss">
    .content {
      //padding-top: 30px;
      max-width: 100%;
      height: auto;
      //border: 2px solid green;
    }
</style>