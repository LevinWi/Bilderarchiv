<template>
    <main @mousemove="handleMousemove">
        <Nav/>
        <nuxt/>
        <Footer/>
        <div id="mouseBall" class="pointer"></div>
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
            document.getElementById('mouseBall').style.left = this.x + "px"
            document.getElementById('mouseBall').style.top = this.y + "px"
            
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
        width: 10rem;
        height: 10rem;
        position: absolute;
        border-radius: 100%;
        left: -10rem;
        top: -10rem;
        transform: translate(-50%, -50%);
        background:#fff;
        mix-blend-mode: difference;
    }
</style>