<template>
  <div class="cards">
    <div class="card" v-for="item in data" :key="item.id">
        <div class="card__body" >
            <div class="card__title"><p>{{item.title}}</p></div>
            <div class="card__type">
              <img v-if="item.type === 'seminar'" src="../assets/icon-traning.svg" alt="Sminar-icon">
              <img v-if="item.type === 'training'" src="../assets/icon-seminar.svg" alt="Sminar-icon">
              <p>{{item.type}}</p>
            </div>
            <div class="card__duration">
              <img  v-if="item.duration" src="../assets/icon-time.svg" alt="Sminar-icon">
              <p>{{item.duration}}</p>
            </div>
            <div class="card__start">
              <img  v-if="item.dateStart" src="../assets/icon-calendar.svg" alt="Sminar-icon">
              <p>{{item.dateStart}}</p>
              </div>
            <div class="card__description">{{item.description}}</div>
            <div class="card__curators" v-if="item.curators">
              <p v-for="curator in item.curators" :key="curator">Куратор: {{curator}}</p>
            </div>
            <div class="card__methodists" v-if="item.methodists">
              <p v-for="methodist in item.methodists" :key="methodist">Методист: {{methodist}}</p>
            </div>
        </div>
    </div> 
  </div>
</template>

<script>

export default {
  name: 'CardOne',
  props: {
    data: Array
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
        font-size: 18px;
        font-weight: 800;
        p {
            margin: 0;
            color: black;
        }
    }
    .card__type {
      display: flex;
      flex-direction: row;
      align-items: center;
      justify-content: flex-start;
      p {
        margin-top: 4px;
        margin-bottom: 4px;
        margin-left: 6px;
      }
      img {
        width: 12px;
        height: 12.7px;
      }
    }
    .card__duration {
      display: flex;
      flex-direction: row;
      align-items: center;
      justify-content: flex-start;
      p {
        margin-top: 4px;
        margin-bottom: 4px;
        margin-left: 6px;
      }
    }
    .card__start {
      display: flex;
      flex-direction: row;
      align-items: center;
      justify-content: flex-start;
      p {
        margin-top: 4px;
        margin-bottom: 4px;
        margin-left: 6px;
      }
    }
</style>