<template>
    <div class="frontpage">
        <img class= "img" @mouseenter="zoom" @mouseleave="shrink" :src="`/pics/logo-stadtmuseum.svg`">


        <div class="row">
            <!-- <input type="checkbox" @click="open" id="hamburg"> -->
            <input type="checkbox" id="hamburg">
            <label  @mouseenter="zoom" @mouseleave="shrink" for="hamburg" class="hamburg">
                <span class="line"></span>
                <span class="line"></span>
            </label>
            <!-- <div id="menu">
                <nuxt-link to="/DSGVO">DSGVO</nuxt-link>
                <nuxt-link to="/impressum">Impressum</nuxt-link>
            </div> -->
        </div>
        <div class="textwrapper">
            <p>Willkommen im Stadtmuseum Aarau. Entdecke unsere neueste Ausstellung vor Ort oder bekomme einen kleinen Einblick auf dieser Webseite. <br> <br>
            Entdecke die Bilder in dem du mit der Lupe über die Seite fährst.</p>
        </div>
        

        <div class="scrollsign"></div>
    </div>
</template>

<script>
export default {
    methods: {
        zoom() {
            var cover = document.getElementById('cover')
            cover.style.width = 500 + 'vw'
        },
        shrink() {
            var cover = document.getElementById('cover');
            cover.style.width = 300 + 'vw'
        }
    //     open() {
    //         if (document.getElementById('menu').style.left == 80 + 'vw') {
    //             document.getElementById('menu').style.left = 100 + "vw"
    //         }
    //         else{
    //             document.getElementById('menu').style.left = 80 + "vw"
    //         }
    //     }
    }
}
</script>

<style scoped>
#menu {
    position: relative;
    left: 100vw;
    top: 10vh;
    height: 90vh;
    width: 20vw;
    transition: left 1s ease;
    background-color: darkblue;
}

.openMenu {
    position: absolute;
    top: 10vh;
    left: 90vw;
}

.frontpage {
    height: 100vh;
    width: 100vw;
    position: relative;
    z-index: 300;
    padding: 2rem 2rem 0 2rem;
}

.img {
    width: 6rem;
}

.textwrapper{
    position: absolute;
    top: 35vh;
    left: 20vw;
    width: 30vw;
}

p { 
    font-size: clamp(1rem, 1.5vw, 3rem);
    color: white;
}

label.hamburg { 
   display: block;
   width: 75px; 
   height: 50px;
   position: relative;
   margin-left: 93%;
   margin-top: -67px;
   border-radius: 4px; 
}

input#hamburg {
    display: none
}

.line { 
   position: absolute; 
   left: 10px;
   height: 1px;
   width: 50px; 
   background: #fff; 
   border-radius: 1.5px;
   display: block; 
   transition: 0.3s; 
   transform-origin: center; 
}

.hamburg:hover .line {
    height: 4px;
}

.line:nth-child(1) { 
    top: 12px; 
}
.line:nth-child(2) {
     top: 24px; 
} 

#hamburg:checked + .hamburg .line:nth-child(1){
   transform: translateY(12px) rotate(-45deg);
}

#hamburg:checked + .hamburg .line:nth-child(2){
    transform: translateY(-0px) rotate(45deg);
}

.scrollsign { 
    position: absolute;
    top: 90vh;
    left: 50vw;
    height: 40px; 
    width: 0px;
}

.scrollsign::after { 
    content: '';
    width: 1px;
    height: 0px;
    display: block;
    background: white;
    animation: border-dance 2s infinite ease;
}

@keyframes border-dance {
    0% {
        height: 0px;
    }

    30% {
        margin-top: 0;
        height: 2rem;
    }

    50% {
        margin-top: 2rem;
        height: 0px;
    }

    100% {
        margin-top: 2rem;
        height: 0px;
    }

}
</style>