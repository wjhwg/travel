<template>
  <div>
    <div class="item" v-for="(item, index) in lists" :key="index">
      <div class="item-title">
        <span class="item-title-icon"></span>
        {{item.title}}
      </div>
      <div v-if="item.children" class="item-children">
          <detail-list :lists="item.children"></detail-list>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'DetailList',
  props: {
    lists: Array
  }
}
</script>
<style lang="stylus" scoped>
  .item-title
    line-height .8rem
    padding 0 .2rem
    font-size .32rem
    .item-title-icon
      position relative
      left .06rem
      top .06rem
      display inline-block
      width .36rem
      height .36rem
      background: url(http://s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.45rem no-repeat
      background-size: .4rem 3rem
      margin-right .1rem
  .item-children
    padding 0 .2rem
</style>
