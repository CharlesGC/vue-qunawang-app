<template>
  <div>
    <div class="title">
      猜你喜欢
    </div>
    <ul>
       <router-link :to="'/detail/' + item.id" tag="li" class="item border-bottom" v-for="item of list" :key="item.id">
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
  name: 'HomeRecommend',
  props: {
    list: Array
  }
}
</script>

<style scoped lang="stylus">
  @import '~styles/mixins.styl'
  .title
    line-height: .8rem
    background #eee
    text-indent .2rem
    margin-top: .2rem
  .item
    display flex
    height:1.9rem
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
        line-height: .54rem
        font-size: .32rem
        ellipse()
      .item-desc
        line-height: .4rem
        color #ccc
        ellipse()
      .item-button
        margin-top: .16rem
        background #ff9300
        border-radius .06rem
        padding 0 .2rem
        line-height: .44rem
        color #fff
</style>
