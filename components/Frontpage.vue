<template>
    <div class="frontpage">
        <img class= "img" :src="`/pics/logo-stadtmuseum.svg`">

        <div class="row">
            <input type="checkbox" id="hamburg">
            <label for="hamburg" class="hamburg">
                <span class="line"></span>
                <span class="line"></span>
            </label>
        </div>

        <p>Hallo wir sind das Stadtmuseum Aarau. Entdecke unsere neueste Ausstellung vor Ort oder bekomme einen kleinen Einblick auf dieser Webseite. <br> <br>
            Suche die Bilder in dem du mit der Lupe über die Seite fährst.</p>

        <div class="scrollsign"></div>
    </div>
</template>

<style scoped>

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

p {
    position: absolute;
    font-family: Arial, Helvetica, sans-serif;
    color: white;
    top: 40vh;
    left: 60vw;
    width: 30vw;
    font-size: 20px;
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
    display:none
}

.line { 
   position: absolute; 
   left:10px;
   height: 1px; width: 50px; 
   background: #fff; border-radius: 1.5px;
   display: block; 
   transition: 0.3s; 
   transform-origin: center; 
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
    border-left: 1.5px solid white;
    height: 40px; 
    width: 6px;
}
</style>