<template>
  <div class="detail">
    <p class="header">
      <span v-if="state == 0" :class="{color:state == 0}">审核中</span>
      <span v-if="state == 1" :class="{color1:state == 1}">已完成</span>
      <span v-if="state == 2" :class="{color2:state == 2}">未通过</span>
    </p>
    <div class="nr">
      <div v-if="state == 0">平台正在审核中请耐心等待</div>
      <div v-if="state == 1">
        <p>已通过平台审核</p>
        <p style="padding-top:0.2rem">请查收佣金</p>
      </div>
      <div v-if="state == 2">
        <p>平台审核中有出现不符合规定</p>
        <p style="padding-top:0.2rem">请再次领取任务</p>
      </div>
    </div>
    <p class="header" style="margin-top:0.26rem">
      <span>任务名称内容</span>
    </p>
  </div>
</template>
<script>
export default {
  data() {
    return {
      msg: "任务详情",
      state: 2
    };
  },
  mounted() {
    // console.log(this.$route.params.id);
    this.$store.commit("headerTab", true);
    this.$store.commit("footerTab", false);
    this.$store.commit("header", "任务详情");
    this.$store.commit("fanhui", true);
  }
};
</script>
<style scoped>
.detail {
  padding-top: 0.88rem;
  min-height: 100%;
  background: #f5f5f5;
}
.color {
  color: #999;
}
.header {
  width: 100%;
  height: 0.8rem;
  background: #fff;
  line-height: 0.8rem;
  font-size: 0.3rem;
  padding-left: 0.3rem;
}
.header > span {
  display: inline-block;
  height: 0.4rem;
  line-height: 0.4rem;
  padding-left: 0.2rem;
  border-left: 2px solid #1e853c;
}
.color1 {
  color: #1e853c;
}
.color2 {
  color: #851e1e;
}
.nr {
  height: 1.4rem;
  margin-top: 0.1rem;
  background: #fff;
  color: #999;
  padding-left: 0.3rem;
  padding-top: 0.3rem;
}
</style>
