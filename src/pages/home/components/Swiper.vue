<template>
<div class='wrapper'>
  <swiper :options="swiperOption" v-if='showSwiper'>
    <!-- slides -->
    <swiper-slide v-for='item of list' v-bind:key='item.id'>
      <img class='swiper-img' :src='item.imgUrl' />
    </swiper-slide>
    <!-- Optional controls -->
    <div class="swiper-pagination"  slot="pagination"></div>
  </swiper>
</div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  props: {
    list: Array
  },
  data: function () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      }
    }
  },
  computed: {
    showSwiper () {
      return this.list.length
    }
  }
}
</script>

<style lang='stylus' scoped>
    .wrapper >>> .swiper-pagination-bullet-active
      background: #fff
    .swiper-img
      width: 100%

</style>
