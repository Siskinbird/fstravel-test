<template>

  <div class="content">
    <Author />
    <CardOne :data="seminars" />
    <CardOne :data="training" />
  </div>
</template>

<script>

import Author from '@/components/Author.vue'
import CardOne from '@/components/CardOne.vue'
import data from '@/assets/jsonData.json'

export default {
  name: 'Content',
  components: {
    Author,
    CardOne
  },
  data() {
    return {
      seminars: data.seminars.filter(el => el.type === 'seminar'),
      training: data.seminars.filter(el => el.type === 'training')
    }
  }
}
</script>


<style scoped lang="scss">
    .content {
      max-width: 100%;
      height: auto;
    }
</style>