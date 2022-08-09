<template>
  <div class="cards">
    <div class="card" v-for="seminar in data.seminars" :key="seminar.id">
        <div class="card__body" >
            <div class="card__title">{{seminar.title}}</div>
            <div class="card__type">{{seminar.type}}</div>
            <div class="card__duration">{{seminar.duration}}</div>
            <div class="card__start">{{seminar.dateStart}}</div>
            <div class="card__description">{{seminar.description}}</div>
        </div>
    </div> 
  </div>
</template>

<script>

import jsonData from '../assets/jsonData.json'

export default {
  name: 'CardOne',
  data() {
    return {
        data: jsonData
    }
  }
}
</script>


<style scoped lang="scss">
    .cards {
      display: flex;
      flex-direction: row;
      flex-wrap: wrap;
      justify-content: flex-start;
      margin-top: 20px;
      max-width: 100%;
      height: auto;
    }
    .card {
        margin-top: 20px;
        margin-left: 30px;
        margin-bottom: 20px;
        width: 200px;
        height: 400px;
        border: 1px solid rgb(227, 221, 221);
        border-radius: 12px;
        box-shadow: 5px 5px 10px 2px rgba(0,0,0,0.2);
        cursor: pointer;
        transition: ease-in-out all .4s;
        &:hover {
          margin-top: 10px;
          box-shadow: 5px 5px 10px 6px rgba(0,0,0,0.2);
        }
    }
    .card__body {
        padding: 15px;

    }
    .card__title {
        font-size: 22px;
        font-weight: 800;
        p {
            color: black;
        }
    }
</style>