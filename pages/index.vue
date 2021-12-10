<template>
    <div class="wrapper">
      <Frontpage/>
      <div class="grid-list">

        <div class="column1">
          <figure v-for="item, index in images" :key="index" :class="item.size">
            <img 
              @mouseover= "handleMouseEnter(`left_${index}`)"
              @mouseleave="hoveredElement=null"
              :src="`/pics/${item.path}`" alt="">
            <p class="image-text-c1" v-if="hoveredElement===`left_${index}`">
              Etiam a vestibulum erat. Sed pharetra odio id magna auctor, non scelerisque felis ornare. Etiam nec mi vehicula, pellentesque ex id, laoreet eros. Donec pulvinar purus tortor, nec posuere nunc egestas nec. Mauris sit amet felis eu neque aliquam mattis. Vestibulum sit amet dictum dui. Pellentesque eu dolor ex. Donec.
            </p>
            
          </figure>
        </div>

        <div class="column2">
          <figure v-for="item, index in images" :key="index" :class="item.size">
            <img 
              @mouseover= "handleMouseEnter(`right_${index}`)"
              @mouseleave="hoveredElement=null"
              :src="`/pics/${item.path}`" alt="">
            <p class="image-text-c2" v-if="hoveredElement===`right_${index}`">
              {{item.size}}, {{item.hasChildren}}
              Etiam a vestibulum erat. Sed pharetra odio id magna auctor, non scelerisque felis ornare. Etiam nec mi vehicula, pellentesque ex id, laoreet eros. Donec pulvinar purus tortor, nec posuere nunc egestas nec. Mauris sit amet felis eu neque aliquam mattis. Vestibulum sit amet dictum dui. Pellentesque eu dolor ex. Donec.
            </p>
          </figure>
        </div>

      </div>
    </div>
</template>

<script>
const DBimages = require('~/assets/data/images.json')
export default {
  data() {
    return {
      title: 'my things',
      images: DBimages,
      color: '',
      hoveredElement: false,
    }
  },
  methods: {
    handleMouseEnter(index){
      this.hoveredElement=index
    }
    }
  
}
</script>