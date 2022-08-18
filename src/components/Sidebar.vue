<template>
  <div class="sidebar" v-show="!mobile">
    <div class="sidebar__logo">
      <img src="../assets/logo.svg" alt="logo">
    </div>
    <MenuPanel :links="profileLinks" />
    <MenuPanel :links="learningLinks" />
    <div class="other-links">
      <span v-for="link in otherLinks" :key="link">{{link}}</span>
    </div>
    <div class="person">
      <div class="person__body">
        <img src="../assets/photo.jpg" alt="User">
        <div class="user">
          <p class="user-name">Екатерина Ивановна</p>
          <div class="user-button">2 458</div>
        </div>
      </div>
      
    </div>
  </div>

<div class="sidebar__mobile">
    <div class="sidebar__logo">
      <img src="../assets/logo.svg" alt="logo">
    </div>


    <div class="hamburger__btn" @click="toggleMobileNav" v-show="mobile" :class="{'is-active' : mobileNav}">
        <span></span>
        <span></span>
        <span></span>
      </div>
  </div>

<transition name="slide-fade">
        <div v-show="mobileNav" class="dropdown-nav">
          <MenuPanel :links="profileLinks" />
          <MenuPanel :links="learningLinks" />
            <div class="other-links">
              <span v-for="link in otherLinks" :key="link">{{link}}</span>
            </div>
          </div>
</transition>


</template>

<script>

import MenuPanel from '@/components/MenuPanel.vue'

export default {
  name: 'Sidebar',
  components: {
    MenuPanel
  },
  data() {
    return {
      windowWidth: null,
      mobileNav: false,
      mobile: false,
      profileLinks: {
        title: "Мой кабинет",
        linlk1: {
          value: "Test link 1",
          href: "#"
        },
        link2: {
          value: "Test link 2",
          href: "#"
        },
        link3: {
          value: "Test link 3",
          href: "#"
        },
      },
      learningLinks: {
        title: "Обучение",
        link1: {
          value: "Семинары и курсы",
          href: "#"
        },
        link2: {
          value: "Вебинары",
          href: "#"
        },
        link3: {
          value: "Самообучение",
          href: "#"
        },
        link4: {
          value: "Тьютор",
          href: "#"
        }
      },
      otherLinks: ["Чат", "Конкурсы", "Онлайн преподавание", "Маркет", "Правила", "Представители"]
    }
  },
  created() {
    window.addEventListener('resize', this.checkScreen);
    this.checkScreen();
  },
  methods: {
    toggleMobileNav() {
      this.mobileNav = !this.mobileNav; 
    },
    checkScreen() {
      this.windowWidth = window.innerWidth;
      if(this.windowWidth <= 768) {
        this.mobile = true;
        return;
      }
      this.mobile = false;
      this.mobileNav = false;
      return;
    } 
  },
}
</script>


<style scoped lang="scss">
    .sidebar {
      display: -webkit-box;
      display: -ms-flexbox;
      display: flex;
      -webkit-box-orient: vertical;
      -webkit-box-direction: normal;
          -ms-flex-direction: column;
              flex-direction: column;
      max-width: 25%;
      height: auto;
      padding: 20px;
      border-radius: 6px;
      background-color: rgb(248, 246, 246);
    }
    .sidebar__logo img{
      @media(max-width: 479px){
        width: 150px;
      }
    }
    .other-links {
      cursor: pointer;
      -webkit-box-flex: 1;
          -ms-flex: 1 0 auto;
              flex: 1 0 auto;
      margin-top: 30px;
      font-weight: 800;
      span {
        display: block;
      }
    }
    .person {
      padding: 5px;
      -webkit-box-flex: 0;
          -ms-flex: 0 0 auto;
              flex: 0 0 auto;
      border-top: 2px solid rgb(221, 218, 218);
      max-width: 100%;
      height: auto; 
      img {
        margin: 10px 15px;
        border-radius: 8px;
      }
    }
    .person__body {
      display: -webkit-box;
      display: -ms-flexbox;
      display: flex;
      -webkit-box-orient: horizontal;
      -webkit-box-direction: normal;
          -ms-flex-direction: row;
              flex-direction: row;
      -webkit-box-align: center;
          -ms-flex-align: center;
              align-items: center;
      font-size: 14px;
      font-weight: 800;
      .user-button {
        cursor: pointer;
        font-size: 12px;
        font-weight: 800;
        margin-top: 12px;
        border-radius: 6px;
        max-width: 35%;
        background-color: rgb(251, 198, 8);
        padding: 2px 0 2px 4px;
      }
      p {
        margin: 0;
      }
    }
    .sidebar__mobile {
      display: none;
      @media(max-width:768px) {
        padding: 20px;
        max-width: 100%;
        display: -webkit-box;
        display: -ms-flexbox;
        display: flex;
        -webkit-box-orient: horizontal;
        -webkit-box-direction: normal;
        -webkit-box-align: center;
            -ms-flex-align: center;
                align-items: center;
        -webkit-box-pack: justify;
            -ms-flex-pack: justify;
                justify-content: space-between;
      }
    }

.hamburger__btn {
  position: relative;
  right: 5.3%;
  width: 24px;
  height: 12px;
  cursor: pointer;
  z-index: 999;
}

.hamburger__btn span {
  width: 24px;
  height: 3px;
  background-color: #000;
  position: absolute;
  top: 10px;
  border-radius: 6px;
  -webkit-transition: 0.3s ease-in-out;
  -o-transition: 0.3s ease-in-out;
  transition: 0.3s ease-in-out;
/*   @media(max-width: 479px){
    right: 40px;
    top: 52px;
  } */
}
.hamburger__btn span:nth-child(1) {
  top: 0;
}
.hamburger__btn span:nth-child(2) {
  top: 6px;
}
.hamburger__btn span:nth-child(3) {
  top: 12px;
}
.hamburger__btn.is-active span {
  background-color: #000;
}
.hamburger__btn.is-active span:nth-child(1) {
  -webkit-transform: rotate(-45deg) translateY(8px);
      -ms-transform: rotate(-45deg) translateY(8px);
          transform: rotate(-45deg) translateY(8px);
}
.hamburger__btn.is-active span:nth-child(2) {
  opacity: 0;
}
.hamburger__btn.is-active span:nth-child(3) {
  -webkit-transform: rotate(45deg) translateY(-8px);
      -ms-transform: rotate(45deg) translateY(-8px);
          transform: rotate(45deg) translateY(-8px);
}

.dropdown-nav {
        border-radius: 8px;
        display: flex;
        flex-direction: column;
        position: fixed;
        width: 100%;
        max-width: 250px;
        height: auto;
        padding: 15px;
        background-color: rgb(248, 246, 246);
        top: 12%;
        right: 8%;
        z-index: 1000;
       @media(max-width: 480px) {
        top: 8%;
        right: 8%;
       }
  }
  .slide-fade-enter-active {
  transition: all 0.3s ease-out;
}

.slide-fade-leave-active {
  transition: all 0.8s;
}

.slide-fade-enter-from,
.slide-fade-leave-to {
  transform: translateX(20px);
  opacity: 0;
}

</style>
