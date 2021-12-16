<template>
    <div class="frontpage">
        <img class="img" @mouseenter="zoom" @mouseleave="shrink" :src="`/pics/logo-stadtmuseum.svg`">

        <div id="menuToggle" class="row">

            <input type="checkbox" id="hamburg">
            <label @mouseenter="zoom" @mouseleave="shrink" for="hamburg" class="hamburg">
                <span class="line"></span>
                <span class="line"></span>
            </label>
           
<!--<input type="checkbox" id="hamburg">
    <label for="hamburg" class="hamburg">
        <span class="line"></span>
        <span class="line"></span>
        <span class="line"></span>
    </label>

        <input type="checkbox" /> 

        <span></span>
        <span></span>-->

            <ul id="menu">
                 <nuxt-link class="nuxtlink" to="/">Home</nuxt-link><br><br>
                 <nuxt-link class="nuxtlink" to="/DSGVO">DSGVO</nuxt-link><br><br>
                 <nuxt-link class="nuxtlink" to="/impressum">Impressum</nuxt-link>
            </ul>

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
            console.log(cover.style.width)
            cover.style.width = 400 + 'vw'
            console.log(cover.style.width)
        },
        shrink() {
            var cover = document.getElementById('cover');
            cover.style.width = 300 + 'vw'
        }
    }
}
</script>

<style scoped>

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
    z-index: 6;
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
   margin-top: 7px;
   border-radius: 4px; 
}

input#hamburg {
    display: none
}

#menuToggle
{
  display: block;
  position: absolute;
  top: 30px;
  right: 50px;
  
  z-index: 1;
  
  -webkit-user-select: none;
  user-select: none;
}

#menuToggle input
{
  display: block;
  width: 50px;
  height: 52px;
  position: absolute;
  top: 7px;
  left: 20px;
  
  cursor: pointer;
  
  opacity: 0; /* hide this */
  z-index: 2; /* and place it over the hamburger */
  
  -webkit-touch-callout: none;
}

/*
 * Make this absolute positioned
 * at the top left of the screen
 */
#menu
{
  position: absolute;
  height: calc(100vh + 120px);
  width: 30vw;
  margin: -120px 0 0 0;
  padding-top: 175px;
  right: -50px;
  
  background: rgba(0, 0, 0, 0.8);
  list-style-type: none;
  z-index: 3;
  -webkit-font-smoothing: antialiased;
  /* to stop flickering of text in safari */
  
  transform-origin: 0% 0%;
  transform: translate(100%, 0);
  
  transition: transform 0.5s cubic-bezier(0.77,0.2,0.05,1.0);
}

#menu li
{
  font-size: 32px;
  padding-left: 50px;
  line-height: 10px;
  padding-bottom: 15px;
}

.nuxtlink
{
  font-size: 32px;
  padding-left: 50px;
  line-height: 12px;
}

/*
 * And let's fade it in from the left
 */
#menuToggle input:checked ~ ul
{
  transform: none;
  opacity: 1;
  color: white;
}



.line { 
   position: absolute; 
   right: 4vw;
   height: 1px;
   width: 50px; 
   background: #fff; 
   border-radius: 1.5px;
   display: block; 
   transition: 0.3s; 
   transform-origin: center; 
   z-index: 8;
}

.hamburg:hover .line {
    height: 3px;
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

#hamburg:checked {
    z-index: 7;
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