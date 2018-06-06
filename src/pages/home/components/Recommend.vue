<template>
  <div>
    <div class="title">猜你喜欢</div>
    <ul>
      <router-link tag="li" :to="'/detail/' + item.id" class="item border-bottom" v-for="item in list" :key="item.id">
        <img class="item-img" :src="item.imgUrl" alt="">
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </router-link>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'Recommend',
  data () {
    return {

    }
  },
  computed: {

  },
  props: {
    list: Array
  }
}
</script>
<style scoped lang="stylus">
  @import '~styles/mixins.styl'
  .title
    margin-top .1rem
    line-height .8rem
    background #eee
    text-indent .2rem
  .item
    display flex
    height 1.9rem
    overflow hidden
    .item-img
      width 1.7rem
      height 1.7rem
      padding .1rem
    .item-info
      flex 1
      padding .1rem
      min-width 0
      .item-title
        font-size .32rem
        line-height .54rem
        ellipsis()
      .item-desc
        line-height .4rem
        color #ccc
        ellipsis()
      .item-button
        background #ff9300
        border-radius .06rem
        color #fff
        margin-top .2rem
        padding 0 .2rem
        line-height .44rem
</style>
