<template>
  <div class="icons">
    <swiper>
      <swiper-slide v-for="(itemFather,index) of page" :key="index">
          <div class="icon" v-for="(item,index) of itemFather" :key="index">
              <div class="icon-img">
                  <img class="icon-img-conent" :src="item.img" alt="">
              </div>
              <p class="icon-desc" v-html="item.title"></p>
          </div>
      </swiper-slide>
    </swiper>
  </div>
</template>
<script>
export default {
  name: 'HomeIcons',
  data () {
    return {
      titleImg: [{
        'title': '景点门票',
        'img': 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png'
      }, {
        'title': '一日游',
        'img': 'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png'
      }, {
        'title': '重庆必游',
        'img': 'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png'
      }, {
        'title': '踏青赏花',
        'img': 'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png'
      }, {
        'title': '室内场馆',
        'img': 'http://img1.qunarzz.com/piao/fusion/1803/fa/2548667cb6e902.png'
      }, {
        'title': '两江夜游',
        'img': 'http://img1.qunarzz.com/piao/fusion/1803/89/55083b0f1951f302.png'
      }, {
        'title': '神秘武隆',
        'img': 'http://img1.qunarzz.com/piao/fusion/1803/96/c70f1e85ae4a4f02.png'
      }, {
        'title': '泡温泉',
        'img': 'http://img1.qunarzz.com/piao/fusion/1803/ab/6f7d6e44963c9302.png'
      }, {
        'title': '泡温泉',
        'img': 'http://img1.qunarzz.com/piao/fusion/1803/ab/6f7d6e44963c9302.png'
      }, {
        'title': '泡温泉',
        'img': 'http://img1.qunarzz.com/piao/fusion/1803/ab/6f7d6e44963c9302.png'
      }, {
        'title': '泡温泉',
        'img': 'http://img1.qunarzz.com/piao/fusion/1803/ab/6f7d6e44963c9302.png'
      }, {
        'title': '泡温泉',
        'img': 'http://img1.qunarzz.com/piao/fusion/1803/ab/6f7d6e44963c9302.png'
      }]
    }
  },
  computed: {
    page () {
      const pages = []
      this.titleImg.forEach((item, index) => {
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
<style lang="stylus" scoped>
    @import '~styles/varibles.styl';
    @import '~styles/mixins.styl';
    .icons  >>> .swiper-container
      overflow hidden
      height 0
      padding-bottom 50%
    .icon
      position relative
      overflow hidden
      float left
      width 25%
      height 0
      padding-bottom 25%
      .icon-img
        position absolute
        top 0
        left 0
        right 0
        bottom .44rem
        box-sizing border-box
        padding .1rem
        .icon-img-conent
          display block
          margin 0 auto
          height 100%
      .icon-desc
        position absolute
        left 0
        right 0
        bottom .24rem
        line-height .44rem
        text-align center
        color $darkTextColor
        ellipsis()
</style>
