<template>
  <div class="contact-popup pfi wh100 not nol z100">
    <div class="wh100 bg pab" @click="closePopup"></div>
    <div class="box centre2 bsb">
      <div class="main wauto">
        <p class="title tc">联系我们</p>
        <div class="form">
          <label class="label" data-name="姓名" id="namelb">
            <input class="ipt" type="text" v-model="name" placeholder="请输入您的姓名" @focus="handlefocus" @blur="handblur">
          </label>
          <label class="label" data-name="电话" id="tellb">
            <input class="ipt" type="text" v-model="tel" placeholder="请输入有效的电话号码" @focus="handlefocus" @blur="handblur">
          </label>
          <label class="label" data-name="邮箱" id="emaillb">
            <input class="ipt" type="text" v-model="email" placeholder="请输入有效的电子邮箱" @focus="handlefocus" @blur="handblur">
          </label>
          <label class="label" data-name="公司" id="companylb">
            <input class="ipt" type="text" v-model="company" placeholder="请输入您所在的公司" @focus="handlefocus" @blur="handblur">
          </label>
          <label class="label">
          <textarea class="w100 textarea bsb" v-model="describe" placeholder="请描述您的问题" @focus="handlefocus" @blur="handblur"></textarea>
          </label>
          <a class="btn db" href="javascript:;" @click="handleSubmit">提交</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data(){
    return{
      name: "",
      tel: "",
      email: "",
      company: "",
      describe: "",
      iserror: false,
      isfetch: false
    }
  },
  methods: {
    closePopup(){
      this.$emit('switchPopupShow');
    },
    handlefocus(e){
      e.target.parentNode.className="label ac";
    },
    handblur(e){
      e.target.parentNode.className="label";
    },
    handleSubmit(){
      if(this.isfetch) return;
      this.isfetch = true;
      let name = this.name.trim();
      let tel = this.tel.trim();
      let email = this.email.trim();
      let name_reg = /^([\u4E00-\u9FA5]){2,11}$/;
      let tel_reg = /^1(3|4|5|7|8)\d{9}$/;
      let email_reg = /^[a-z0-9]+([._\\-]*[a-z0-9])*@([a-z0-9]+[-a-z0-9]*[a-z0-9]+.){1,63}[a-z0-9]+$/;
      if(!name_reg.test(name)){
        document.getElementById("namelb").className="label error";
        this.iserror = true;
      }
      if(!tel_reg.test(tel)){
        document.getElementById("tellb").className="label error";
        this.iserror = true;
      }
      if(!email_reg.test(email)){
        document.getElementById("emaillb").className="label error";
        this.iserror = true;
      }
      if(this.iserror){
        this.isfetch = false;
        return;
      }else{
        // fetch
        this.isfetch = false; //放在回调中
      }
    }
  }
}
</script>
<style lang="less" scoped>
  .contact-popup{
    .bg{
      background-color: rgba(22,22,22,.5);
    }
    .box{
      width: 17.5088rem;
      padding: 72px 0;
      background-color: #fff;
      border-radius: 5px;
      .main{
        width: 500px;
      }
      .title{
        margin-bottom: 50px;
        font-size: 34px;
        color: #2e2e2e;
      }
      .label{
        position: relative;
        display: block;
        line-height: 48px;
        margin-bottom: 13px;
        border: 1px solid #d8d8d8;
        border-radius: 3px;
        overflow: hidden;
        &.ac{
          border: 1px solid #667dc7;
        }
        &.error{
          border: 1px solid red;
        }
        &::before{
          content: attr(data-name);
          position: absolute;
          left: 0;
          top: 0;
          display: inline-block;
          height: 48px;
          padding-left: 20px;
          font-size: 14px;
          color: #2e2e2e;
        }
        .ipt{
          display: block;
          width: calc(100% - 74px);
          height: 48px;
          margin-left: 74px;
        }
      }
      .textarea{
        height: 125px;
        padding: 15px;
        font-size: 14px;
        color: #2e2e2e;
      }
      .btn{
        height: 50px;
        line-height: 50px;
        margin-top: 14px;
        font-size: 20px;
        color: #fff;
        text-align: center;
        background-color: #667dc7;
        border-radius: 3px;
      }
    }
  }
</style>
