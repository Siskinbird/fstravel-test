<template>
  <div class="sidebar__mobile">
    <div class="sidebar__logo">
      <img src="../assets/logo.svg" alt="logo">
    </div>
    <div class="hamburger__btn" @click="activeBtn =! activeBtn" :class="{'is-active': activeBtn}">
        <span></span>
        <span></span>
        <span></span>
      </div>
  </div>
  <div class="sidebar">
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
      activeBtn: false,
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
  }
}
</script>


<style scoped lang="scss">
    .sidebar {
      display: flex;
      flex-direction: column;
      max-width: 385px;
      height: auto;
      margin-right: 10px;
      border-radius: 6px;
      background-color: rgb(248, 246, 246);
      @media(max-width: 768px) {
        display: none;
      }
    }
    .sidebar__logo img{
      flex: 0 0 auto;
      margin: 20px;
      width: 300px;
      height: auto;
      position: relative;
      top:0px;
      left: 0px;
      @media(max-width: 479px){
        width: 150px;
      }
    }
    .other-links {
      cursor: pointer;
      flex: 1 0 auto;
      margin-top: 30px;
      font-weight: 800;
      span {
        margin-left: 20px;
        padding: 2px;
        display: block;
      }
    }
    .person {
      padding: 5px;
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
      display: flex;
      flex-direction: row;
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
        max-width: 100%;
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: space-between;
      }
    }

.hamburger__btn {
  position: relative;
  top: 15px;
  width: 64px;
  height: 48px;
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
  transition: 0.3s ease-in-out;
  @media(max-width: 479px){
    right: 40px;
    top: 52px;
  }
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
  transform: rotate(-45deg) translateY(8px);
}
.hamburger__btn.is-active span:nth-child(2) {
  opacity: 0;
}
.hamburger__btn.is-active span:nth-child(3) {
  transform: rotate(45deg) translateY(-8px);
}


</style>
