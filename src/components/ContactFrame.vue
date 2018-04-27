<template>
  <div class="contact-frame pfi z50 hauto2">
    <div class="item">
      <i class="ico sn1"></i>
      <div class="pab text">023-6300 0111</div>
    </div>
    <div class="item">
      <i class="ico sn2"></i>
    </div>
    <div class="item">
      <i class="ico sn3"></i>
      <div class="pab text">younakeji@163.com</div>
    </div>
    <div class="item" @click="openPopup">
      <i class="ico sn4"></i>
    </div>
    <div class="item" @click="backToTop">
      <i class="ico sn5"></i>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    backToTop(){
      let timer=setInterval(function(){
        let ct = document.documentElement.scrollTop || document.body.scrollTop;
        // 每次移动100px
        ct -= 100;
        if(ct>0){
          //如果与顶部的距离大于零
          window.scrollTo(0,ct);
        }
        else{
          //如果距离小于等于零,到顶部
          window.scrollTo(0,0);
          clearInterval(timer);
        }
      },20)
    },
    openPopup(){
      this.$emit('switchPopupShow');
    }
  }
}
</script>
<style lang="less" scoped>
  .contact-frame{
    right: 26px;
    top: 50%;
    border: 1px solid #d9d9d9;
    .item{
      position: relative;
      padding: 7px;
      border-bottom: 1px solid #d9d9d9;
      background: #fff;
      &:last-of-type{
        border: none;
      }
      .text{
        display:none;
        right: 50px;
        top: -1px; 
        height: 49px;
        line-height: 49px;
        padding: 0 20px;
        font-size: 20px;
        white-space:nowrap;
        color: #657ccb;
        border: 1px solid #d9d9d9;
        border-right: none;
        background-color: #fff;
      }
      .ico{
        display: block;
        width: 35px;
        height: 35px;
        background-image: url(../assets/img/contact-icon.png);
        background-repeat: no-repeat;
        &.sn2{
          background-position: 0 -35px;
        }
        &.sn3{
          background-position: 0 -70px;
        }
        &.sn4{
          background-position: 0 -105px;
        }
        &.sn5{
          background-position: 0 -140px;
        }
      }
      &:hover {
        background: #657ccb;
        .ico{
          background-image: url(../assets/img/contact-icon-active.png);
        }
        .text{
          display: block;
        }
      }

    }
  }
</style>
