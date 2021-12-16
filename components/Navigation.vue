<template>
    <div class="row">
        <input type="checkbox" @click="open" id="hamburg">
        <label for="hamburg" class="navigation">
            <span class="line"></span>
            <span class="line"></span>
        </label>
        <div id="menu">
            <ul>
                <li><nuxt-link to="/">Home</nuxt-link></li>
                <li><nuxt-link to="/DSGVO">DSGVO</nuxt-link></li>
                <li><nuxt-link to="/impressum">Impressum</nuxt-link></li>
            </ul>
            <img :src="`/pics/logo-stadtmuseum.svg`" alt="logo">
        </div>
    </div>
</template>

<script>
export default {
    methods: {
        open() {
            if (document.getElementById('menu').style.left == 67 + 'vw') {
                document.getElementById('menu').style.left = 100 + "vw"
            }
            else {
                document.getElementById('menu').style.left = 67 + "vw"
            }
        }
    }
}
</script>

<style scoped>
    
    #menu {
        z-index: 999;
        position: fixed;
        left: 100vw;
        top: 0;
        height: 100vh;
        width: 33vw;
        padding: 30vh 3vw;
        transition: left 1s ease;
        background-color: rgba(0, 0, 0, 0.5);
        border-left: 0.1vw rgba(255, 255, 255, 0.1) solid;
    }

    #menu ul li {
        text-align: right;
        font-size: clamp(1rem, 6vw, 4rem);
    }

    #menu ul li a{
        cursor: none;
    }

    #menu ul li a::after {
        content: '';
        width: 50%;
        height: 1px;
        margin-left: 100%;
        display: block;
        background: white;
        transition: .3s;
        opacity: 0;
    }

    #menu ul li a:hover::after {
        margin-left: 50%;
        opacity: 1;
    }  

    #menu img {
        position: absolute;
        bottom: 10vh;
        right: 3vw;
        width: 30%;
    }

    .navigation { 
        z-index: 1000;
        display: block;
        cursor: none;
        border-radius: 4px; 
        position: fixed;
        width: 10vw;
        height: 5vw;
        top: 2vw;
        right: 0;
    }

    #menuToggle input {
        display: block;
        pointer-events: none;
        position: absolute;
        width: 3vw;
        height: 2vw;
        top: 2vw;
        right: 2vw;
        opacity: 0;
        z-index: 1000; 
        -webkit-touch-callout: none;
        cursor: none;
    }

    #hamburg {
        z-index: 1001;
    }

    input#hamburg {
        display: none;
    }

    .line { 
        position: absolute; 
        height: 1px;
        width: 8vw; 
        background: #fff; 
        border-radius: 1.5px;
        display: block; 
        transition: 0.3s; 
        transform-origin: center; 
        z-index: 1001;
    }

    .line:nth-child(1) { 
        top: 50%; 
    }
    .line:nth-child(2) {
        top: calc(50% + 24px); 
    } 

    .navigation:hover .line {
        height: 5px;
    }

    #hamburg:checked + .navigation .line:nth-child(1){
        transform: translateY(24px) rotate(-45deg);
    }

    #hamburg:checked + .navigation .line:nth-child(2){
        transform: translateY(-0px) rotate(45deg);
    }

    #hamburg:checked {
        z-index: 7;
    }

</style>