<template>
  <div class="wrapper">
    <Sidebar />
    <Content />
  </div>

</template>

<script>
import Sidebar from './components/Sidebar.vue'
import Content from './components/Content.vue'

export default {
  name: 'App',
  components: {
    Sidebar,
    Content
  }
}
</script>

<style lang="scss">

@import url(./normalize.css);

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
.container {
  max-width: 1440px;
  padding: 20px;
  margin: 0 auto;
}
.wrapper {
  max-width: 1440px;
  display: flex;
  flex-direction: row;
  margin: 0 auto;
  @media(max-width:768px) {
    flex-direction: column;
  }
}

</style>
