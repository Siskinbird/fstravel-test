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
      learnLink: {
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
  }/* ,
  methods: {
    toggleOpen: function(index) {
      this.links = this.links.map((menu__panel, i) => {
        if(index === i) {
          menu__panel.open = !menu__panel.open;
        }
        return menu__panel;
      })
    }
  }, */
}
</script>


<style scoped lang="scss">
    .sidebar {
      max-width: 385px;
      height: auto;
      margin-right: 10px;
      //border: 2px solid black;
      border-radius: 6px;
      padding: 30px;
      background-color: rgb(248, 246, 246);
    }
    .sidebar__logo img{
      width: 500px;
      height: auto;
      position: relative;
      top:0px;
      left: 0px;
    }
/*     a {
      text-decoration: none;
      font-size: 32px;
      color: black;
      margin-top: 20px;
    }
    ul {
      padding: 0;
      list-style: none;
      font-weight: 600;
    }
    li {
      margin-top: 20px;
    }
    .menu a {
      border-radius: 16px;
      transition: ease all .5s;
      padding: 10px;
       &:hover {
        padding: 10px 0 10px 20px;
      }
    }
    .menu__list {
      position: relative;
      &:hover {
        .menu__drop {
          opacity: 1;
        }
      }
    }
    .menu__drop {
      position: absolute;
      left: 50%;
      opacity: 0;
    }
     */
</style>
