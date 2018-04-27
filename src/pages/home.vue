<template>
  <div>
    <!-- 联系浮动框 -->
    <contact-frame @switchPopupShow="switchOpenState" />
    <num-animation :num=23 />
    <!-- 页面头部 -->
    <div class="pagetop dn">
      <div class="box wauto">
        <img class="logo fl" src="../assets/img/logo.png" alt="logo">
        <div class="main h100 fr">
          <a class="link ac" href="javascript:;">首页</a>
          <a class="link" href="#solveplan">解决方案</a>
          <a class="link" href="#service">定制服务</a>
          <a class="link" href="#standard">服务标准</a>
          <a class="link" href="#levelopment">发展历程</a>
          <a class="link" href="#enterprise">合作企业</a>
          <a class="link" href="#pagebottm">公司介绍</a>
        </div>
      </div>
    </div>

    <!-- 轮播 -->
    <swiper class="swiper dn" :options="swiperOption" ref="mySwiper">
      <swiper-slide class="slide">
        <div class="icon wh100 pre" style="background-image:url(./static/img/swiper-pic.jpg)">
          <div class="title icon centre1" style="background-image:url(./static/img/swiper-text.png)"></div>
        </div>
      </swiper-slide>
      <swiper-slide class="slide">
        <div class="icon wh100 pre" style="background-image:url(./static/img/swiper-pic.jpg)">
          <div class="title icon centre1" style="background-image:url(./static/img/swiper-text.png)"></div>
        </div>
      </swiper-slide>
      <swiper-slide class="slide">
        <div class="icon wh100 pre" style="background-image:url(./static/img/swiper-pic.jpg)">
          <div class="title icon centre1" style="background-image:url(./static/img/swiper-text.png)"></div>
        </div>
      </swiper-slide>
      <div class="swiper-pagination w100" slot="pagination"></div>
    </swiper>


    <!-- 鹰 -->
    <div class="introduce pre" id="solveplan">
      <div class="left pre">
        <img class="line wh100" src="../assets/img/line.png" alt="">
        <a class="btn ac" href="javascript:;" data-index="0" @click="switchEagle">巨鹰</a>
        <a class="btn" href="javascript:;" data-index="1" @click="switchEagle">赤腹鹰</a>
        <a class="btn" href="javascript:;" data-index="2" @click="switchEagle">苍鹰</a>
        <a class="btn" href="javascript:;" data-index="3" @click="switchEagle">雀鹰</a>
        <div :class="`pab main ${eagle.sn}`" id="circularbox">
          <img class="circular wh100" src="../assets/img/circular.png" alt="">
          <div class="grail pab group">
            <p class="name fe">{{eagle.name}}</p>
            <i class="separate"></i>
            <p class="title fe">{{eagle.title}}</p>
          </div>
        </div>
      </div>
      <div class="right pab">
        <div :class="`item ${eagle.sn}`">
          <h4 class="title">{{eagle.title}}</h4>
          <p class="text">{{eagle.text}}</p>
          <div class="phrases">
            <p class="phrase sn1">{{eagle.list[0]}}</p>
            <p class="phrase sn2">{{eagle.list[1]}}</p>
            <p class="phrase sn3">{{eagle.list[2]}}</p>
          </div>
        </div>
      </div>
    </div>

    <!-- 应用 -->
    <div class="application pre" id="service">
      <h4 class="title tc dib wauto2 pab">多款协同应用供您选择</h4>
      <p class="text pab wauto2">不同类型的企业可以选择自己需要的办公应用，拒绝功能堆砌、资源闲置</p>
      <img class="pic pab nob wauto2" src="../assets/img/machine-hand.png" alt="">
      <div class="icons flex sn1 pab">
        <div class="one grail">
            <i class="icon sn1">新闻<br>管理</i>
            <i class="icon sn2">待办<br>事宜</i>
            <i class="icon sn3">流程<br>管理</i>
            <i class="icon sn4">日历<br>管理</i>
            <i class="icon sn5">任务<br>管理</i>
        </div>
        <div class="two grail">
            <i class="icon sn1">通讯<br>录</i>
            <i class="icon sn2">邮件<br>管理</i>
            <i class="icon sn3">公文<br>管理</i>
            <i class="icon sn4">scm<br>流程</i>
        </div>
        <div class="three grail">
            <i class="icon sn1">会议<br>管理</i>
            <i class="icon sn2">合同<br>审批</i>
            <i class="icon sn3">工作<br>沟通</i>
        </div>
        <div class="four grail">
            <i class="icon sn1">论坛<br>管理</i>
            <i class="icon sn2">考勤<br>管理</i>
        </div>
      </div>
      <div class="icons flex sn2 pab">
        <div class="one grail">
            <i class="icon sn1">知识<br>仓库</i>
            <i class="icon sn2">工作<br>记录</i>
            <i class="icon sn3">知识<br>问答</i>
            <i class="icon sn4">专家<br>网络</i>
            <i class="icon sn5">爱关怀</i>
        </div>
        <div class="two grail">
            <i class="icon sn1">项目<br>查看</i>
            <i class="icon sn2">测评</i>
            <i class="icon sn3">收款<br>查看</i>
            <i class="icon sn4">我的<br>业绩</i>
        </div>
        <div class="three grail">
            <i class="icon sn1">我的<br>客户</i>
            <i class="icon sn2">合同<br>审批</i>
            <i class="icon sn3">客户<br>需求</i>
        </div>
        <div class="four grail">
            <i class="icon sn1">消息<br>管理</i>
            <i class="icon sn2">工作<br>总结</i>
        </div>
      </div>
    </div>

    <!-- 服务指标 -->
    <div class="quota pre">
      <h4 class="title tc dib wauto2 pab">优纳科技帮助企业实现信息化管理</h4>
      <p class="text pab wauto2">大数据助力，实现高价值管理</p>
      <div class="show tc pre">
        <div class="item">
          <div class="data dib">
            <div class="symbol1">-</div>
            <div class="num">70</div>
            <div class="symbol2">
              <b class="arrow-down dib"></b>
              <b class="percentage">%</b>
            </div>
          </div>
          <p class="title2">企业IT成本费用</p>
          <p class="text2">按需定制高效协同<br>企业级业务保障<br>高可靠、高安全</p>
        </div>
        <div class="item">
          <div class="data dib">
            <div class="symbol1">-</div>
            <div class="num">30</div>
            <div class="symbol2">
              <b class="arrow-down dib"></b>
              <b class="percentage">%</b>
            </div>
          </div>
          <p class="title2">每年节省运营成本</p>
          <p class="text2">从人力、财务、办公耗材成本等<br>各个维度上都在帮助企业<br>重新量化目标</p>
        </div>

        <div class="item">
          <div class="data dib">
            <div class="symbol1">+</div>
            <div class="num">300</div>
            <div class="symbol2">
              <b class="arrow-up dib"></b>
              <b class="percentage">%</b>
            </div>
          </div>
          <p class="title2">单位时间内审批效率</p>
          <p class="text2">智能化网络办公和移动办公<br>全面提升业务审批效率<br>&nbsp;</p>
        </div>

        <div class="item">
          <div class="data dib">
            <div class="symbol1">-</div>
            <div class="num">50</div>
            <div class="symbol2">
              <b class="arrow-down dib"></b>
              <b class="percentage">%</b>
            </div>
          </div>
          <p class="title2">财务工作出错率</p>
          <p class="text2">高效集成多部门数据共享<br>精准审批财务流程<br>&nbsp;</p>
        </div>
      </div>
    </div>

    <!-- 服务流程 -->
    <div class="process pre">
      <h4 class="title tc dib wauto2 pab">定制服务流程</h4>
      <p class="text pab wauto2">优纳科技提供产品设计、定制开发、整体方案设计与规划三大类服务，优质的业务流程</p>
      <img class="pic wauto2 pab" src="../assets/img/service-flow.png" alt="">
    </div>

    <!-- 服务标准 -->
    <div class="standard pre" id="standard">
      <h4 class="title tc dib wauto2 pab">服务标准</h4>
      <p class="text pab wauto2">根据各类业务，优纳科技提供标准化的工作流程，有效机制保障项目整体质量</p>
      <div class="cards pre tc">
        <div class="card">
          <img class="pic" src="../assets/img/standard1.png" alt="">
          <i class="shadow"></i>
          <p class="title">方案合理</p>
          <p class="words">融会贯通各行业经营模式<br>为你量身定制最合理的<br>项目养成计划</p>
        </div>
        <div class="card">
          <img class="pic" src="../assets/img/standard2.png" alt="">
          <i class="shadow"></i>
          <p class="title">交付准时</p>
          <p class="words">10年项目管控经营<br>确保你的项目<br>每一个节点</p>
        </div>
        <div class="card">
          <img class="pic" src="../assets/img/standard3.png" alt="">
          <i class="shadow"></i>
          <p class="title">质量可靠</p>
          <p class="words">严格按照流程开发<br>工匠精神打造产品<br>每一个细节</p>
        </div>
        <div class="card">
          <img class="pic" src="../assets/img/standard4.png" alt="">
          <i class="shadow"></i>
          <p class="title">服务贴心</p>
          <p class="words">深入贯彻全民客服的理念<br>360度跟进你的需求<br>&nbsp;</p>
        </div>
      </div>
    </div>

    <!-- 发展历程 -->
    <div class="levelopment pre" id="levelopment">
      <h4 class="title tc dib wauto2 pab">发展历程</h4>
      <img class="pic wauto2 pab" src="../assets/img/development-history.png" alt="">
    </div>

    <!-- 合作企业 -->
    <div class="enterprise pre" id="enterprise">
      <h4 class="title tc dib wauto2 pab">创业路上，相伴企业成长</h4>
      <img class="pic wauto2 pab" src="../assets/img/brand-show.png" alt="">
    </div>

    <!-- 页面底部 -->
    <div class="pagebottm pre" id="pagebottm">
      <div class="pic pre wauto fix">
        <img class="logo fl" src="../assets/img/logo.png" alt="logo">
      </div>
      <div class="main pre wauto">
        <div class="top flex">
          <p class="words">
            优纳科技集团成立于2010年,注册资金1100万，现有员工500余人。是2016年度中国最具竞争力和成长力的互联网公司之一。作为重庆市互联网+行业的龙头企业，
            是目前国内最全面的人力资源咨询、信息共享优质互联网平台公司致力成为中国互联网行业领先的互联网综合服务公司。其业务范围涵盖互联网产品、企业管理软件、智慧医疗、智慧建筑四大板块。
          </p>
          <div class="links">
            <div class="flex">
              <a class="link" href="javascript:;">解决方案</a>
              <a class="link" href="javascript:;">定制服务</a>
              <a class="link" href="javascript:;">服务标准</a>
            </div>
            <div class="flex">
              <a class="link" href="javascript:;">产品中心</a>
              <a class="link" href="javascript:;">合作企业</a>
              <a class="link" href="javascript:;">公司介绍</a>
            </div>
          </div>
        </div>
        <div class="bottom flex">
          <div class="contact">
            <p class="tel">023-6300 0111</p>
            <p class="email">咨询邮箱：service@younatianxia.com</p>
          </div>
          <div class="info">
            <p>@2018 yongna 渝icp备 103030303号 - 2  重庆公网备 1110002020220号</p>
            <p>重庆市南岸区南滨路钟楼广场长江当代美术馆4楼</p>
          </div>
        </div>
      </div>
    </div>

    <!-- 联系我们 -->
    <contact-popup v-show="isOpenPopup" @switchPopupShow="switchOpenState" />
    
  </div>
</template>

<script>
import { swiper, swiperSlide } from 'vue-awesome-swiper'
import 'swiper/dist/css/swiper.css'
import ContactFrame from '@/components/ContactFrame'
import ContactPopup from '@/components/ContactPopup'
import NumAnimation from '@/components/NumAnimation'



export default {
  name: 'home',
  data() {
    return {
      isOpenPopup: false,
      swiperOption: {
        notNextTick: true,
        autoplay: 3000,
        loop: true,
        pagination: {
          el: '.swiper-pagination'
        }
      },
      eagles:[
        {
          sn: 'sn1',
          name: '巨鹰',
          title: '大数据分析',
          text: '既能实现OA系统内部各模块间的数据整合，如借款与报销、预算与决算等，也能实现OA系统与其他业务系统间的数据整合，如ERP、CRM、HR、档案系统、财务系统等，帮助企业消除信息孤岛，实现数据的互享互通。',
          list:[
            '灵便的实现数据整合和数据统计，消除信息孤岛',
            'OA系统内部工作流之间的数据整合',
            '实现OA系统工作流与其他业务系统之间的数据整合'
          ]
        },
        {
          sn: 'sn2',
          name: '赤腹鹰',
          title: '以管理层为中心',
          text: '既能实现OA系统内部各模块间的数据整合，如借款与报销、预算与决算等，也能实现OA系统与其他业务系统间的数据整合，如ERP、CRM、HR、档案系统、财务系统等，帮助企业消除信息孤岛，实现数据的互享互通。',
          list:[
            '企业核心数据一键生成',
            '透视全公司各层级',
            '人才鉴别与培养'
          ]
        },
        {
          sn: 'sn3',
          name: '苍鹰',
          title: '轻量化前端渠道',
          text: '对各渠道独立的多个运营管理功能及界面进行横向整合，形成统一的运营管理工作台。运营人员可在该平台上对内容、系统参数等信息进行统一配置管理或按流程开展日常运营操作，提升运营效率。',
          list:[
            '支持移动建模，满足企业个性化的移动应用',
            'APP手机端,web移动端,Pad移动端,微信集成，多端同步',
            '统一运营管理工作台，同步内容、系统参数等信息'
          ]
        },
        {
          sn: 'sn4',
          name: '雀鹰',
          title: '即时消息处理',
          text: '可通过内置的便捷线上沟通工具进行即时消息回复，进行有效的沟通。消息发出“已读或未读”一目了然。“业务往来”和“工作往来”的集成展示在沟通中也能随时掌握信息、处理待办事项。',
          list:[
            '企业组织架构生成通讯录，快速查找联系人',
            '“已读或未读”一目了然，消息100%传达',
            '一键分享，审批流程轻松查看，加快审批进度'
          ]
        }
      ],
      eagle: {
        sn: 'sn1',
        name: '巨鹰',
        title: '大数据分析',
        text: '既能实现OA系统内部各模块间的数据整合，如借款与报销、预算与决算等，也能实现OA系统与其他业务系统间的数据整合，如ERP、CRM、HR、档案系统、财务系统等，帮助企业消除信息孤岛，实现数据的互享互通。',
        list:[
          '灵便的实现数据整合和数据统计，消除信息孤岛',
          'OA系统内部工作流之间的数据整合',
          '实现OA系统工作流与其他业务系统之间的数据整合'
        ]
      },
    }
  },
  created() { 
    this.$nextTick(() => {
      window.addEventListener('scroll', () => {
        let scrollTop = document.documentElement.scrollTop;
        console.log(scrollTop);
      }, false)
    }) 
  },
  methods: {
    switchEagle(e){
      document.querySelectorAll("#solveplan .left .ac")[0].className = "btn";
      e.target.className = "btn ac";
      let index = parseInt(e.target.getAttribute("data-index"));
      this.eagle = this.eagles[index];
    },
    switchOpenState(){
      this.isOpenPopup = !this.isOpenPopup;
    }
  },
  components:{
    swiper,
    swiperSlide,
    ContactFrame,
    ContactPopup,
    NumAnimation
  }
}
</script>
<style src="../assets/css/home.less" lang="less" scoped />
<style>
.swiper-pagination{
  bottom: 10px;
  left: 0;
  width: 100%;
}
.swiper-pagination-bullet {
  background-color: #ccc !important;
}
.swiper-pagination-bullet-active {
  width: 25px;
  border-radius: 3px !important;
  background-color: #c9cbd2 !important;
  -webkit-transform-origin:0 4px;
  transform-origin:0 4px;
  -webkit-transition: width 0.3s;	
  transition: width 0.3s;
}

</style>

