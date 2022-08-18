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
//import data from '@/assets/jsonData.json'

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
      errors: []
      //seminars: data.seminars.filter(el => el.type === 'seminar'),
      //training: data.seminars.filter(el => el.type === 'training')
    }
  },
  async mounted() {
    try {
      const response = await fetch(this.dataUrl)
      const result = await response.json()
      console.log(result)
      this.seminars.push(...result.seminars.filter(el => el.type === 'seminar'))
      this.training.push(...result.seminars.filter(el => el.type === 'training'))
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
      max-width: 100%;
      height: auto;
    }
</style>