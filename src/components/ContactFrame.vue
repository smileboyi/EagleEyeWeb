<template>
  <div class="contact-frame pfi">
    <div class="item"></div>
    <div class="item"></div>
    <div class="item"></div>
    <div class="item"></div>
    <div class="item"></div>
  </div>
</template>

<script>
export default {
  
}
</script>
<style lang="less" scoped>
  .contact-frame{
    right: 26px;
    top: 50%;
    .item{
      width: 35px;
      height: 35px;
      background: url(../assets/img/contact-icon.png) no-repeat;
      &:nth-of-type(2){
        background-position: 0 -35px;
      }
      &:nth-of-type(3){
        background-position: 0 -70px;
      }
      &:nth-of-type(4){
        background-position: 0 -105px;
      }
    }
  }
</style>
