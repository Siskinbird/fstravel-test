<template>
  <div class="sidebar">
    <div class="sidebar__logo">
      <img src="../assets/logo.svg" alt="">
    </div>
    <MenuPanel v-for="(menu__panel, i) in links" :menu__panel="menu__panel" 
    :index="i" 
    :key="i"
    :open="menu__panel.open"
    @toggleOpen = "toggleOpen" />
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
      links: [
        {
          title: "Мой кабинет",
          link: ["first", "second", "third"],
          open: false
          },
          {
          title: "Обучение",
          link: ["Семинары и курсы", "Вебинары", "Самообучение", "Тьютор"],
          open: false
        }
      ]
    }
  },
  methods: {
    toggleOpen: function(index) {
      this.links = this.links.map((menu__panel, i) => {
        if(index === i) {
          menu__panel.open = !menu__panel.open;
        }
        return menu__panel;
      })
    }
  },
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
