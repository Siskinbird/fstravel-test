<template>
    <div class="menu">
        <div :class="open ? 'menu__panel open' : 'menu__panel'" @click="$emit('toggleOpen', index)">
            <div class="title">{{menu__panel.title}}</div>
            <div class="links">{{menu__panel.link}}</div>
        </div>
    </div>    
</template>

<script>
export default {
    name: 'MenuPanel',
    props: ['menu__panel', 'index', 'open'],
}
</script>

<style scoped lang="scss">
    .menu {
        margin-top: 40px;
    }

    
    .menu__panel {
        font-size: 24px;    
        .title{
            cursor: pointer;
            font-weight: 800;
            position: relative;
            transition: all .4s linear;
            &::after {
                content: '';
                position: absolute;
                top: 50%;
                right: 0;
                transform: translateY(-50%) rotate(90deg);
                width: 30px;
                height: 30px;
                background-image: url('../assets/arrow-next.svg');
                background-position: center;
                background-size: contain;
                background-repeat: no-repeat;
                transition: all .4s linear;
            }
        }
    }
    .menu__panel {
        .links {
            font-size: 24px;
            opacity: 0;
            max-height: 0px;
            overflow-y: hidden;
            transition: all .4s ease-out;
        }
    }
    .menu__panel.open  {
        .title {
        margin-bottom: 15px;
        &::after {
            transform: translateY(-50%) rotate(180deg);
        }
    }
    }
    .menu__panel.open .links {
        opacity: 1;
        max-height: 1000px;
    }

</style>