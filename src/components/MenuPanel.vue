<template>
    <div class="menu">
        <div :class="isOpen? 'menu__panel open' : 'menu__panel'" @click="isOpen = !isOpen">
            <div class="title">{{links.title}}</div>
            <div class="links" v-for="link in links" :key="link.value">
                <span v-if="typeof link === 'object'">{{link.value}}</span>
            </div>
        </div>
    </div>    
</template>

<script>
export default {
    name: 'MenuPanel',
    props: {
        links: {
            type: Object,
            required: true,
        },        
    },
    data() {
        return {
            isOpen: false
        }
    }
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
        margin-left: 20px;
        margin-right: 20px;
        .links {
            font-size: 18px;
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
        margin-left: 20px;
        cursor: pointer;
    }

</style>