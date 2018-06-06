<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page, index) in pages" :key="index">
        <div class="icon"  v-for="item in page" :key="item.id">
          <div class="icon-img">
            <img class="icon-imgcontent" :src="item.imgUrl" alt="">
          </div>
          <p class="icon-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>
<script>
export default {
  name: 'HomeIcons',
  data () {
    return {
      swiperOption: {
        pagination: {
          el: '.swiper-pagination'
        },
        loop: false
      }
    }
  },
  props: {
    list: Array
  },
  computed: {
    pages () {
      const pages = []
      this.list.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }

}
</script>
<style scoped lang="stylus">
  @import '~styles/varibles.styl'
  @import '~styles/mixins.styl'
  .icons >>> .swiper-container
    height: 0
    padding-bottom: 50%
  .icons
    margin-top .1rem
    .icon
      overflow hidden
      position relative
      width 25%
      padding-bottom 25%
      float left
      height 0
      .icon-img
        position absolute
        top 0
        right 0
        left 0
        bottom .44rem
        box-sizing border-box
        padding .1rem
        .icon-imgcontent
          height  100%
          display block
          margin 0 auto
      .icon-desc
        position absolute
        bottom 0
        left 0
        right 0
        text-align center
        height .44rem
        line-height .44rem
        color $darkTextColor
        ellipsis()
</style>
