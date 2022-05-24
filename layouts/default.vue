<template>
    <main @mousemove="handleMousemove">
        <Navigation/>
        <nuxt/>
        <svg version="1.1" id="cover" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" viewBox="0 0 1920 1080" style="enable-background:new 0 0 1920 1080;" xml:space="preserve">
            <path class="black" d="M0,0v1080h1920V0H0z M960,611.85c-39.68,0-71.85-32.17-71.85-71.85s32.17-71.85,71.85-71.85s71.85,32.17,71.85,71.85
	        S999.68,611.85,960,611.85z"/>
        </svg>        
    </main>
</template>

<script>
export default {
    data() {
        return {
            x: 0,
            y: 0,
            mouseScrollOffset: 0
        }
    },
    mounted() {
        document.addEventListener('scroll', this.handleScrollMousemove)
    },
    methods: {
        handleScrollMousemove(event){
            this.y = document.documentElement.scrollTop + this.mouseScrollOffset;
            this.updateMouseBallPos();
        },
        handleMousemove(event){            
            this.x = event.pageX;
            this.y = event.pageY;            
            this.mouseScrollOffset = this.y - document.documentElement.scrollTop;
            this.updateMouseBallPos();
        },
        updateMouseBallPos(){
            document.getElementById('cover').style.left = this.x + "px"
            document.getElementById('cover').style.top = this.y + "px"
        }
    }   
}
</script>

<style>
    body {
        cursor: none;
        background: #111;
    }

    main {
        position: relative;
        overflow: hidden;
    }

    .nuxt-link-exact-active {
        display: none;
    }

    .black {
        opacity: 0.95;
    }

    .navigation { 
        cursor: pointer!important;
    }

    #menuToggle{
        cursor: pointer!important;
    }

    #menu {
        cursor: initial;
    }

    #cover{
        position: absolute;
        transform: translate(-50%, -50%);
        top: 0;
        left: 0;
        width: 300vw;
        height: 300vh;
        pointer-events: none;
        z-index: 200;
        overflow: hidden;
        transition: width .6s ease;
    }

    ::-webkit-scrollbar {
        display: none;
    }

    ::selection {
        background:darkred;
        color: white;
    }

    ::-moz-selection {
        background:darkred;
        color: white;
    }
    
</style>