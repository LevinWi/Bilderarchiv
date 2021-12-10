<template>
    <div class="wrapper">
      <Frontpage/>
      <img class="BG-img" :src="`/pics/stadtmuseum_aarau.png`" alt="">
      <div class="grid-list">
        <div class="column1">
          <figure v-for="item, PhotoId in images" :key="PhotoId" :class="item.size">
            <img 
              v-if="item.PhotoId%2==0"
              @mouseover= "handleMouseEnter(`left_${PhotoId}`)"
              @mouseleave="hoveredElement=null"
              :src="item.Link" :alt="item.AltText">
            <p class="image-text-c1" v-if="hoveredElement===`left_${PhotoId}`">
              Titel: {{item.TextTitle}} <br> {{item.Description}}
            </p>
            
          </figure>
        </div>

        <div class="column2">
          <figure v-for="item, PhotoId in images" :key="PhotoId" :class="item.size">
            <img v-if="item.PhotoId%2!=0" @mouseover= "handleMouseEnter(`right_${PhotoId}`)" @mouseleave="hoveredElement=null" :src="item.Link" :alt="item.AltText">
            <p class="image-text-c2" v-if="hoveredElement===`right_${PhotoId}`">
               Titel: {{item.TextTitle}} <br> {{item.Description}}
            </p>
          </figure>
        </div>

      </div>
    </div>
</template>

<script>
export default {
  data() {
    return {
      title: 'my things',
      images: [],
      color: '',
      hoveredElement: false,
    }
  }, 
  async created() {
    const DBimages = await this.$axios.get('https://webex-groupc.azurewebsites.net/api/Photo')
    
    this.images = DBimages.data
    console.log(DBimages.data)
  },
  methods: {
    handleMouseEnter(index){
      this.hoveredElement=index
    }
  }
  
}
</script>

<style>
  .BG-img {
    width: 80vw;
    position: absolute;
    top: 10vh;
    left: 10vw;
  }
</style>