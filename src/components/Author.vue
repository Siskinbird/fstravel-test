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
    <div class="about" v-for="author in data" :key="author">
        <div class="description">
            <h3>{{author.topic}}</h3>
            <h2>{{author.name}}</h2>
            <p>{{author.description}}</p>
        </div>
        <div class="avatar">
            <img :src="author.avatar" alt="author avatar">
        </div>
    </div>
   </div>
</template>

<script>

export default {
  name: 'Author',
  props: {
    data: Array
  }
}
</script>


<style scoped lang="scss">
    .author {
      max-width: 98%;
      height: auto;
      margin: 20px auto;
      text-align: left;
    }
    .top__title {
        margin-bottom: 30px;
      display: -webkit-box;
      display: -ms-flexbox;
      display: flex;
      -webkit-box-orient: horizontal;
      -webkit-box-direction: normal;
      -webkit-box-align: center;
          -ms-flex-align: center;
      -webkit-box-pack: justify;
          -ms-flex-pack: justify;
              justify-content: space-between;
    }
    .top__title-left {
      p {
        font-size: 42px;
        font-weight: 700;
      }
      span {
        color: rgb(180, 176, 176);
      }
      @media(max-width:768px) {
        p {
        font-size: 24px;
      }
      @media(max-width: 479px){
        p {
          font-size: 18px;
        }
      }
        }
    }
    .top__title-right {
        color: rgb(115, 115, 235);
        font-size: 20px;
        font-weight: 600;
        p {
            cursor: pointer;
            font-weight: 800;
        }
        @media(max-width:768px) {
            font-size: 14px;
        }
        @media(max-width: 479px){
            p {
                font-size: 12px;
            }
       }
    }
    .about {
        display: -webkit-box;
        display: -ms-flexbox;
        display: flex;
        -webkit-box-orient: horizontal;
        -webkit-box-direction: normal;
            -ms-flex-direction: row;
                flex-direction: row;
        -webkit-box-align: center;
            -ms-flex-align: center;
        -webkit-box-pack: start;
            -ms-flex-pack: start;
                justify-content: flex-start;
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
        @media(max-width:768px) {
            p {
              font-size: 16px;
              line-height: 20px;  
            }
       }
       
       @media(max-width: 479px){
        -webkit-box-orient: vertical;
        -webkit-box-direction: normal;
            -ms-flex-direction: column;
                flex-direction: column;
         .avatar {
            -webkit-box-ordinal-group: 0;
                -ms-flex-order: -1;
                    order: -1;
        }
        img {
            width: 120px;
            height: 120px;
        }
      }
        
    }
    .description {
        max-width: 660px;
        @media(max-width:768px) {
            max-width: 440px;
        }
    }
</style>