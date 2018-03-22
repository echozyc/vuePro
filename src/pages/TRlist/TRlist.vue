<template>
  <div class="hh">
    <Headerflag></Headerflag>
    <div class="content-ul" v-for="(b,index) in allbrands.brand" :key="index">
      <p>{{b.order}}</p>
      <div class="content-li" v-for="(list,index) in b.list">
        <div>
          <div>
            <img :src='list.logo' alt="">
          </div>
        </div>
        <p>{{list.name}}</p>
        <p>{{list.address}}</p>
      </div>
    </div>
    <div class="list">
      <ul>
        <li>A</li>
        <li>B</li>
        <li>C</li>
        <li>D</li>
        <li>E</li>
        <li>F</li>
        <li>G</li>
        <li>H</li>
        <li>I</li>
        <li>J</li>
        <li>K</li>
        <li>L</li>
        <li>M</li>
        <li>N</li>
        <li>O</li>
        <li>P</li>
        <li>Q</li>
        <li>R</li>
        <li>S</li>
        <li>T</li>
        <li>U</li>
        <li>V</li>
        <li>W</li>
        <li>X</li>
        <li>Y</li>
        <li>Z</li>
      </ul>
    </div>
  </div>
</template>

<script>
  import Headerflag from '../../components/Headerflag/Headerflag.vue'
  import {mapState} from 'vuex'
  import BScroll from 'better-scroll'
  export default {
    components:{
      Headerflag
    },
    computed:{
      ...mapState(['allbrands'])
    },
    mounted(){
      this.$store.dispatch('getallbrands')
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus">
.hh
  margin-right 0
  overflow hidden
  .content-ul
    p
      width 100%
      height 24px
      background transparent
      font-size  12px
      color #999
      display flex
      align-items center
      padding-left 20px
    .content-li
      width 100%
      height 73px
      background #ffffff
      padding-right 20px
      box-sizing border-box
      position relative
      >div
        width 100%
        background-color #ffffff
        padding 10px
        box-sizing border-box
        border-bottom 1px solid #f5f5f5
        >div
          width 90px
          box-sizing border-box
          padding 5px
          background #ffffff
          border 1px solid #f5f5f5

          img
            width 100%
      p:nth-child(2)
        width 50%
        position absolute
        top 7px
        left 90px
        font-size 16px
        color #000000
      p:nth-child(3)
        width 50%
        position absolute
        top 28px
        left 94px
  .list
    position fixed
    right 0
    top 50%
    transform translateY(-50%)
    li
      font-size 12px
      color  #666

</style>
