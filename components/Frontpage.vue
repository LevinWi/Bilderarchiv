<template>
    <div class="frontpage">
        <img class= "img" src="~/assets/frontpageimg/logo-stadtmuseum.svg">

   <div class="row">
    <input type="checkbox" id="hamburg">
    <label for="hamburg" class="hamburg">
        <span class="line"></span>
        <span class="line"></span>
    </label>
    </div>

    <img class= "img2" src="~/assets/frontpage/stadtmuseum_aarau.png">

    <p>Hallo wir sind das Stadtmuseum Aarau. Entdecke unsere neueste Ausstellung vor Ort oder bekomme einen kleinen Einblick auf dieser Webseite. <br> <br>
    Suche die Bilder in dem du mit der Lupe über die Seite fährst.</p>

    <div class="scrollsign"></div></p>
    </div>
</template>

<style scoped>
    .frontpage {
        height: 100vh;
        width: 100vw;
        position: relative;
        z-index: 300;
        background-color: rgb(22, 10, 3);
    }
    .frontpage p {
        font-size: clamp(1rem, 2vh, 2rem);
        color: lemonchiffon;
    }
    .background {
    background-color: black;
}

.img {
    height: 6.5vh;
    margin: 1.5% 0 0 3%;
}

.img2 {
    height: 50vh;
    margin: 10% 0 0 10%;
}

p {
font-family: Arial, Helvetica, sans-serif;
color: white;
background-color: black;
margin: -10% 20% -50% 52%;
font-size: 20px;
}


label.hamburg { 
   display: block;
   background: black; width: 75px; height: 50px;
   position: relative;
   margin-left: 93%;
   margin-top: -67px;
   border-radius: 4px; 
}

input#hamburg {display:none}

.line { 
   position: absolute; 
   left:10px;
   height: 1px; width: 50px; 
   background: #fff; border-radius: 1.5px;
   display: block; 
   transition: 0.3s; 
   transform-origin: center; 
}

.line:nth-child(1) { top: 12px; }
.line:nth-child(2) { top: 24px; } 

#hamburg:checked + .hamburg .line:nth-child(1){
   transform: translateY(12px) rotate(-45deg);
}

#hamburg:checked + .hamburg .line:nth-child(2){
    transform: translateY(-0px) rotate(45deg);
}


.scrollsign { 
  border-left: 1.5px solid white;
  height: 40px; width: 6px;
  margin-left: 50%;
  margin-top: 59%;
}
</style>