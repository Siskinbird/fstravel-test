<template>
  <div class="sidebar">
    <div class="sidebar__logo">
      <img src="../assets/logo.svg" alt="">
    </div>
    <MenuPanel :links="profileLinks" />
    <MenuPanel :links="learningLinks" />
    <div class="other-links">
      <span v-for="link in otherLinks" :key="link">{{link}}</span>
    </div>
    <div class="person">Hello</div>
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
      //border: 2px solid black;
      border-radius: 6px;
      //padding: 30px;
      background-color: rgb(248, 246, 246);
    }
    .sidebar__logo img{
      flex: 0 0 auto;
      margin: 20px;
      width: 300px;
      height: auto;
      position: relative;
      top:0px;
      left: 0px;
    }
    .other-links {
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
      flex: 0 0 auto;
      border-top: 2px solid rgb(221, 218, 218);
      max-width: 100%;
      height: 40px;
    }
</style>
