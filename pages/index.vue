<template>
    <div class="wrapper">
      <Frontpage/>
      <img class="BG-img" :src="`/pics/stadtmuseum_aarau.png`" alt="">
      <div class="grid-list">
        <div class="column1">
          <figure v-for="item, PhotoId in images" :key="PhotoId" :class="item.size">
            <img  v-if="item.PhotoId%2==0" @mouseover= "handleMouseEnter(`left_${PhotoId}`)" @mouseleave="hoveredElement=null" :src="item.Link" :alt="item.AltText">
            <div class="column1-text">
              <transition name="fade">
                <h3 class="image-title-c1" v-if="hoveredElement===`left_${PhotoId}`">
                  {{item.TextTitle}}
                </h3>
              </transition>
              <transition name="fade">
                <p class="image-text-c1" v-if="hoveredElement===`left_${PhotoId}`">
                  {{item.Description}}
                </p>
              </transition>
            </div>
            
          </figure>
        </div>

        <div class="column2">
          <figure v-for="item, PhotoId in images" :key="PhotoId" :class="item.size">
            <img v-if="item.PhotoId%2!=0" @mouseover= "handleMouseEnter(`right_${PhotoId}`)" @mouseleave="hoveredElement=null" :src="item.Link" :alt="item.AltText">
            <div class="column2-text">
              <transition name="fade">
                <h3 class="image-title-c2" v-if="hoveredElement===`right_${PhotoId}`">
                  {{item.TextTitle}}
                </h3>
              </transition>
              <transition name="fade">
                <p class="image-text-c2" v-if="hoveredElement===`right_${PhotoId}`">
                  {{item.Description}}
                </p>
              </transition>
            </div>
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
  },
  methods: {
    handleMouseEnter(index){
      this.hoveredElement=index
    }
  }
  
}
</script>

<style>
  .fade-enter-active{
    transition: opacity 3s;
    transition-delay: 1s;
  }
  .fade-leave-active {
    transition: opacity 1s;
  }
  .fade-enter, .fade-leave-to {
    opacity: 0;
  }
  .BG-img {
    width: 80vw;
    position: absolute;
    top: 10vh;
    left: 10vw;
  }
</style>