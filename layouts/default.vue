<template>
    <main @mousemove="handleMousemove">
        <Nav/>
        <nuxt/>
        <Footer/>
        <div id="mouseBall" class="pointer"></div>
         <svg version="1.1" id="cover" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" viewBox="0 0 1920 1080" style="enable-background:new 0 0 1920 1080;" xml:space="preserve">
            <path class="black" d="M0,0v1080h1920V0H0z M960,596c-30.9,0-56-25.1-56-56s25.1-56,56-56s56,25.1,56,56S990.9,596,960,596z"/>
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
            console.log(this.mouseScrollOffset)
            this.updateMouseBallPos();
        },
        handleMousemove(event){            
            this.x = event.pageX;
            this.y = event.pageY;            
            this.mouseScrollOffset = this.y - document.documentElement.scrollTop;
            this.updateMouseBallPos();
        },
        updateMouseBallPos(){
            document.getElementById('mouseBall').style.left = this.x + "px"
            document.getElementById('mouseBall').style.top = this.y + "px"
            document.getElementById('cover').style.left = this.x + "px"
            document.getElementById('cover').style.top = this.y + "px"
            
            //this.$refs.mouseBall.style.left = this.x + "px"
            //this.$refs.mouseBall.style.top = this.y + "px"
        }
    }   
}
</script>

<style>
    body {
        cursor: none;
        background: #111;
    }
    .nuxt-link-exact-active {
        font-weight: 700;
    }
    .pointer {
        pointer-events: none;
        content: "";
        z-index: 999;
        width: 290px;
        height: 290px;
        position: absolute;
        border-radius: 100%;
        left: -10rem;
        top: -10rem;
        transform: translate(-50%, -50%);
        background:rgb(225, 255, 255);
        mix-blend-mode: difference;
    } 
    .black {
        /* background-color: rgba(0,0,0,0.5); */
        opacity: 0.9;
    }
    #cover{
        position: absolute;
        transform: translate(-50%, -50%);
        top: 0;
        left: 0;
        width: 300vw;
        height: 300vh;
        pointer-events: none;
        z-index: 100;
        overflow: hidden;
    }
    a:hover>#cover{
        transform: scale(1.2) ;
    }
    ::-webkit-scrollbar {
        display: none;
    }

</style>