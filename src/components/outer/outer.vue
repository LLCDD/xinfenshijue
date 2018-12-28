<template>
  <div class="outer">{{ msg }}</div>
</template>
<script>
export default {
  data() {
    return {
      msg: "关于我们"
    };
  },
  mounted() {
    this.$store.commit("headerTab", true);
    this.$store.commit("footerTab", false);
    this.$store.commit("header", "关于我们");
    this.$store.commit("fanhui", true);
  }
};
</script>
<style scoped="">
.outer {
  padding-top: 0.88rem;
  background: #f5f5f5;
  min-height: 100%;
}
</style>

