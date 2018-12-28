<template>
  <div class="team">
    <p>
      <span class="tuandu">一级团队</span>
      <span class="ren">{{ one }}人</span>
    </p>
    <p>
      <span class="tuandu">二级团队</span>
      <span class="ren">{{ two }}人</span>
    </p>
  </div>
</template>
<script>
export default {
  data() {
    return {
      one: "1",
      two: "1"
    };
  },
  mounted() {
    this.$store.commit("headerTab", true);
    this.$store.commit("footerTab", false);
    this.$store.commit("header", "我的团队");
    this.$store.commit("fanhui", true);
  }
};
</script>
<style scoped="">
.team {
  min-height: 100%;
  background: #f5f5f5;
  padding-top: 0.88rem;
}
.team > p {
  height: 0.84rem;
  line-height: 0.84rem;
  padding-left: 0.3rem;
  padding-right: 0.3rem;
  background: #fff;
  border-bottom: 2px solid #f5f5f5;
}
.tuandu {
  color: #1e853c;
  font-size: 0.28rem;
}
.ren {
  float: right;
  color: #999999;
}
</style>
