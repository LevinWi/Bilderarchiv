<template>
    <div class="wrapper">
      <Frontpage/>
      <div class="grid-list">
        <div class="column1">
          <figure v-for="item, index in images" :key="index" :class="item.size">
          <img :src="`/pics/${item.path}`" alt="">
          <p class="image-text-c1">{{item.size}}, {{item.hasChildren}}</p>
          </figure>
        </div>
        <div class="column2">
          <figure v-for="item, index in images" :key="index" :class="item.size">
          <img :src="`/pics/${item.path}`" alt="">
          <p class="image-text-c2">{{item.size}}, {{item.hasChildren}}</p>
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
    }
  },
}
</script>