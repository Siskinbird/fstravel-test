<template>
  <div class="author">
    <div class="top__title">
        <div class="top__title-left">
            <p>Витрина <span>Семинары и курсы</span></p>
        </div>
        <div class="top__title-right">
            <p>Моё обучение</p>
        </div>
    </div>
    <div class="about">
        <div class="description">
            <h3>{{data.author.topic}}</h3>
            <h2>{{data.author.name}}</h2>
            <p>{{data.author.description}}</p>
        </div>
        <div class="avatar">
            <img :src="data.author.avatar">
        </div>
    </div>
   </div>
</template>

<script>

import jsonData from '../assets/jsonData.json'

export default {
  name: 'Author',
  data() {
    return {
        data: jsonData
    }
  }
}
</script>


<style scoped lang="scss">
    .author {
      max-width: 98%;
      height: auto;
      border: 4px solid blue;
      margin: 0 auto;
      text-align: left;
    }
    .top__title {
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: space-between;
    }
    .top__title-left {
        margin: 0;
        padding: 5px;
        p {
            margin: 10px;
            font-size: 42px;
            font-weight: 700;
        }
        span {
            color: rgb(180, 176, 176);
        }
    }
    .top__title-right {
        color: rgb(115, 115, 235);
        font-size: 20px;
        font-weight: 600;
        padding-right: 100px;
        p {
            cursor: pointer;
            font-weight: 800;
        }
    }
    .about {
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: flex-start;
        margin: 10px;
        padding: 10px;
        h3 {
            text-transform: uppercase;
            font-weight: 800;
            font-size: 16px;
        }

        h2 {
            margin: 0;
            font-size: 32px;
            font-weight: 800;
        }

        img {
            width: 150px;
            height: 150px;
            border-radius: 50%;
        }

        p {
            line-height: 24px;
            font-size: 20px;
            font-weight: 400;
        }
    }
    .description {
        max-width: 660px;
    }
</style>