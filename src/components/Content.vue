<template>

  <div class="content">
    <Author :data="author" />
    <CardOne :data="seminars" />
    <CardOne :data="training" />
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
  },
  data() {
    return {
      dataUrl: 'https://eg-cdn.s3.eu-central-1.amazonaws.com/static/fe-test/seminars-test-data.json',
      seminars: [],
      training: [],
      author: [],
      errors: []
    }
  },
  async mounted() {
    try {
      const response = await fetch(this.dataUrl)
      const result = await response.json()
      this.seminars.push(...result.seminars.filter(el => el.type === 'seminar'))
      this.training.push(...result.seminars.filter(el => el.type === 'training'))
      this.author.push(result.author)
      console.log(this.author)
      console.log(this.seminars)
      console.log(this.training)
    }
    catch(error) {
    this.errors.push(error)
  } 
  } 
}
</script>


<style scoped lang="scss">
    .content {
      padding: 20px;
      max-width: 75%;
      height: auto;
    }
</style>