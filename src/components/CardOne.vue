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
              <img src="../assets/icon-calendar.svg" alt="Sminar-icon">
              <p>Сессия: {{dataTime(item.dateStart)}}</p>
              </div>
            <div class="card__description">{{item.description}}</div>
            <div class="card__curators" v-if="item.curators">
              <p v-for="curator in item.curators" :key="curator">Куратор: {{curator}}</p>
            </div>
            <div class="card__methodists" v-if="item.methodists">
              <p v-for="methodist in item.methodists" :key="methodist">Методист: {{methodist}}</p>
            </div>
            <div class="card__price" v-if="item.price"><p>{{item.price}} P</p></div>
            <div class="card__tarif" v-if="item.type === 'training'"><p>Выбрать тариф</p></div>

        </div>
    </div> 
  </div>
</template>

<script>

import moment from 'moment';

export default {
  name: 'CardOne',
  methods: {
    dataTime(value) {
      moment.lang('ru')
      return moment(value).format('DD MMMM')
    }
  },
  props: {
    data: Array
  },

}
</script>


<style scoped lang="scss">
    .cards {
      display: flex;
      flex-direction: row;
      flex-wrap: wrap;
      justify-content: flex-start;
      max-width: 100%;
      height: auto;
      @media(max-width: 1166px) {
        font-size: 12px;
        justify-content: space-around;
       }
       @media(max-width:768px) {
        font-size: 12px;
       }
       
    }
    .card {
        position: relative;
        margin-top: 20px;
        margin-left: 30px;
        margin-bottom: 20px;
        width: 240px;
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
        @media(max-width:768px) {
          width: 220px;
        }
        @media(max-width:479px) {
          width: 280px;
          margin: 20px;
          margin: 20px auto;
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
         @media(max-width:768px) {
          font-size: 16px;
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

    .card__price {
      position: absolute;
      display: flex;
      align-items: center;
      justify-content: center;
      bottom: 30px;
      right: 30px;
      background-color: rgb(251, 198, 8);
      border-radius: 8px;
      width: 100px;
      transition: all ease-in-out .4s;
      p {
        color: #fff;
        font-size: 16px;
        font-weight: 800;
        margin: 10px auto;
      }
      &:hover{
        box-shadow: 5px 0 5px 2px rgba(0,0,0,0.2);
        bottom: 25px;
      }
    }
    .card__tarif {
      position: absolute;
      display: flex;
      align-items: center;
      justify-content: center;
      bottom: 30px;
      right: 20px;
      background-color: rgb(62, 140, 248);
      border-radius: 8px;
      width: 180px;
      transition: all ease-in-out .4s;
      p {
        color: #fff;
        font-size: 16px;
        font-weight: 800;
        margin: 10px auto;
      }
      &:hover{
        box-shadow: 5px 0 5px 2px rgba(0,0,0,0.2);
        bottom: 25px;
      }
      @media(max-width:768px) {
          width: 130px;
          p {
            font-size: 14px;
          }
       }
    }
</style>