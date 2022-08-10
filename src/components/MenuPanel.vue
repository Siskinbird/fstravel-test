<template>
    <div class="menu">
        <div :class="isOpen? 'menu__panel open' : 'menu__panel'" @click="isOpen = !isOpen">
            <div class="title">{{links.title}}</div>
            <div class="links" v-for="link in links" :key="link.value">
                <span v-if="typeof link === 'object'">{{link.value}}</span>
            </div>
        </div>
    </div> 
    <!-- <div class="menu__mobile" >
        <div :class="isOpen? 'menu__panel open' : 'menu__panel'" @click="isOpen = !isOpen">
            <div class="title">{{links.title}}</div>
            <div class="links" v-for="link in links" :key="link.value">
                <span v-if="typeof link === 'object'">{{link.value}}</span>
            </div>
        </div>
    </div> -->   
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
            isOpen: false,
            mobileNav: false
        }
    },
}
</script>

<style scoped lang="scss">
    .menu {
        margin-top: 40px;
    }

    
    .menu__panel {
        font-size: 16px;    
        .title{
            cursor: pointer;
            font-weight: 800;
            position: relative;
            -webkit-transition: all .4s linear;
            -o-transition: all .4s linear;
            transition: all .4s linear;
            &::after {
                content: '';
                position: absolute;
                top: 50%;
                right: 0;
                -webkit-transform: translateY(-50%) rotate(90deg);
                    -ms-transform: translateY(-50%) rotate(90deg);
                        transform: translateY(-50%) rotate(90deg);
                width: 16px;
                height: 16px;
                background-image: url('../assets/arrow-next.svg');
                background-position: center;
                background-size: contain;
                background-repeat: no-repeat;
                -webkit-transition: all .4s linear;
                -o-transition: all .4s linear;
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
            -webkit-transition: all .4s ease-out;
            -o-transition: all .4s ease-out;
            transition: all .4s ease-out;
            &:hover {
                background-color: yellow;
            }
        }
    }
    .menu__panel.open  {
        .title {
        margin-bottom: 15px;
        &::after {
            -webkit-transform: translateY(-50%) rotate(180deg);
                -ms-transform: translateY(-50%) rotate(180deg);
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
    .menu__mobile {
        -webkit-transition: t;
        -o-transition: t;
        transition: t;
    }
</style>