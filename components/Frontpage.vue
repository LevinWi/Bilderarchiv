<template>
    <div class="frontpage">
        <img class= "img" :src="`/pics/logo-stadtmuseum.svg`">

        <div id="menuToggle" class="row">

           <input type="checkbox" id="hamburg">
            <label for="hamburg" class="hamburg">
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
                <a href="#"><li>Home</li></a>
                 <a href="#"><li>About</li></a>
                 <a href="#"><li>Info</li></a>
                 <a href="#"><li>Contact</li></a>
                 <a href="#" target="_blank"><li>Show me more</li></a>
            </ul>
        </div>

        <h1>Hello there!</h1>

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
    z-index: 6;
}

h1 {
    font-family: 'Mrs Eaves XL', Times, serif;
    color: #fff;
    padding-top: 1vh;
    padding-left: 55vw;
    width: 100vw;
    font-size: 9rem;
    line-height: 1;
}

p {
    position: absolute;
    font-family: Arial, Helvetica, sans-serif;
    color: white;
    top: 40vh;
    left: 57vw;
    width: 30vw;
    font-size: 20px;
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
    display:none
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
  height: 32px;
  position: absolute;
  top: -7px;
  left: 15px;
  
  cursor: pointer;
  
  opacity: 0; /* hide this */
  z-index: 2; /* and place it over the hamburger */
  
  -webkit-touch-callout: none;
}


/*
 * Just a quick hamburger
 */
/*#menuToggle span
{
  display: block;
  width: 50px;
  height: 3px;
  margin-bottom: 5px;
  position: relative;
  
  box-shadow: 0px 2px 0px red;

  border-radius: 1px;
  
  z-index: 1;
  
  transform-origin: center;
  
  transition: transform 0.5s cubic-bezier(0.77,0.2,0.05,1.0),
              background 0.5s cubic-bezier(0.77,0.2,0.05,1.0),
              opacity 0.55s ease;
}

#menuToggle span:first-child
{
  transform-origin: 0% 0%;
}

#menuToggle span:nth-last-child(2)
{
  transform-origin: 0% 100%;
}

/* 
 * Transform all the slices of hamburger
 * into a crossmark.
 */
/*#menuToggle input:checked ~ span
{
  opacity: 1;
  transform: rotate(45deg) translate(-2px, -1px);
  /*background: red;*/
/*}

/*
 * But let's hide the middle one.
 */
/*#menuToggle input:checked ~ span:nth-last-child(3)
{
  opacity: 0;
  transform: rotate(0deg) scale(0.2, 0.2);
}*/

/*
 * Ohyeah and the last one should go the other direction
 */
/*#menuToggle input:checked ~ span:nth-last-child(2)
{
  opacity: 1;
  transform: rotate(-45deg) translate(1px, 10px);
}*/

/*
 * Make this absolute positioned
 * at the top left of the screen
 */
#menu
{
  position: absolute;
  height: calc(100vh + 120px);
  width: 100vw;
  margin: -120px 0 0 0;
  padding-top: 155px;
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
  padding: 20px 0;
  font-size: 32px;
  padding-left: 200px;
  line-height: 22px;
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
   left:-50px;
   height: 1px; width: 50px; 
   background: #fff; border-radius: 1.5px;
   display: block; 
   transition: 0.3s; 
   transform-origin: center; 
   z-index: 8;
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
    border-left: 1.5px solid white;
    height: 40px; 
    width: 6px;
}
</style>