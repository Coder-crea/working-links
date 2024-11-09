<template>
    <div class="nav">
        <div class="logo"><router-link to="/">Belle Manicure</router-link></div>
        <ul class="nav-links" v-if="screenWidth > 1024">
            <li class="active"><router-link to="/">Home</router-link></li>
            <li><a href="">About</a></li>
            <li><a href="">Sources</a></li>
            <li><router-link to="/tarrifs">Prices</router-link></li>
        </ul>
        <i v-else :class="menuIcon" @click="showMenu()"></i>

        <ul class="nav-links-mobile" v-if="screenWidth <= 1024 && mobileMenu">
            <li class="active"><a href="">Home</a></li>
            <li><a href="">About</a></li>
            <li><a href="">Sources</a></li>
            <li><router-link to="/tarrifs">Price</router-link></li>
        </ul>
    </div>
</template>

<script>
export default {
    data(){
        return {
            screenWidth: screen.width,
            mobileMenu: false,
            menuIcon: "fa-solid fa-bars"
        }
    },
    mounted(){
        this.onScreenResize()
    },
    methods: {
        onScreenResize(){
            window.addEventListener("resize", ()=>{
                this.screenWidth= screen.width
            })
        },
        showMenu(){
            this.mobileMenu = !this.mobileMenu
            this.menuIcon = this.menuIcon.includes("bars") ? "fa-solid fa-xmark" : "fa-solid fa-bars"
        }
    }
}
  
</script>

<style lang="scss" scoped>
.nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-top: 30px;
    flex-wrap: wrap;
    
    .logo {
        font-size: 25px;
        font-family: "Playwrite GB S", cursive;
        font-weight: 400;
        font-style: italic;
        color: #fff;
        cursor: pointer;
        transition: all 0.4s ease;
        &:hover {
            color: #7f7c7c;
        }
    }
    .nav-links {
        list-style: none;
        display: flex;
        li {
           
            &:not(:last-of-type) {
                margin-right: 25px;
            }
        }
    }
    .nav-links-mobile {
        list-style: none;
        text-align: center;
        width: 100%;
        li {
            margin-top: 25px;
        }
    }
}
</style>