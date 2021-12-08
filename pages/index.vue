<template>
    <div class="wrapper">
      <Frontpage/>
      
      <h1>This site is the index</h1>
      <div class="grid-list">
        <figure v-for="item, index in images" :key="index" :class="item.size">
          <img :src="`/pics/${item.path}`" alt="">
          <p>{{item.size}}, {{item.hasChildren}}</p>
        </figure>
      </div>
    </div>
</template>

<script>
const images = require('~/assets/data/images.json')
export default {
  data() {
    return {
      title: 'my things',
      images: images,
      color: '',
    }
  },
}
</script>