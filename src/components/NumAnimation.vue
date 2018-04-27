<template>
  <div>
    <slot></slot>
    <div class="num-box">
      <div class="nums">
        <div class="num">0</div>
        <div class="num">1</div>
        <div class="num">2</div>
        <div class="num">3</div>
        <div class="num">4</div>
        <div class="num">5</div>
        <div class="num">6</div>
        <div class="num">7</div>
        <div class="num">8</div>
        <div class="num">9</div>
        <div class="num">0</div>
        <!-- <div class="num">1</div>
        <div class="num">2</div>
        <div class="num">3</div> -->
      </div>
    </div>

  </div>
</template>
<script>
export default {
  props:{
    num:Number
  },
  created() {
    let numArr = [...this.num.toString()];
    console.log(numArr);
    numArr.map(num => {
      this.createNumBox(parseInt(num));
    })
  },
  methods:{
    createNumBox(num){
      let nums = [0,1,2,3,4,5,6,7,8,9,0];
      let i = 1;
      while(i <= num){
        nums.push(i);
        i +=1 ;
      }
      console.log(nums);
    }
  }
}
</script>
<style lang="less" scoped>
  .num-box{
    height: 1rem;
    .nums{
      height: 1000%;
      transform: translateY(-100%);
      -webkit-transition: -webkit-transform 3s;
      -webkit-transition: transform 3s;
    }
    .num{
      height: 1rem;
      line-height: 1rem;
    }



  }
</style>

