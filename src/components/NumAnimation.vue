<template>
  <div class="num-box flex ovh" :id="`num${num}`"  :data-num="`${this.num}`"></div>
</template>
<script>
export default {
  props:{
    num:Number
  },
  mounted() {
    let _html ="";
    let ele = document.getElementById(`num${this.num}`);
    [...this.num.toString()].map(num => {
      _html += this.createNumBox(parseInt(num));
    })
    ele.innerHTML = _html;
  },
  methods:{
    createNumBox(num){
      let nums = [0,1,2,3,4,5,6,7,8,9,0];
      let i = 0;
      while(i < num){
        nums.push(++i);
      }
      let style= `transform: translateY(-1${num}0%)`;
      let html = `<div class="nums fe in" style="${style}">`;
      nums.map(num => {
        html += `<div class="num">${num}</div>`;
      });
      html += '</div>';
      return html;
    }
  }
}
</script>
<style lang="less">
  .num-box{
    margin: 0 2px;
    height: 1.5439rem;
    line-height: 1.5439rem;
    font-size: 1.4035rem;
    .nums{
      height: 1000%;
      -webkit-transition: transform 3s;
      &.in{
        transform: translateY(0) !important;
      }
    }
    .num{
      font-size: 1.4035rem;
    }
  }
</style>

