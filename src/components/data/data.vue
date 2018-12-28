<template>
  <div class="div">
    <p class="personal">
      <span>个人资料</span>
    </p>
    <div class="xx">
      <p>
        <span>姓名</span>
        <input style="height:88%" type="text" placeholder="输入真实姓名" v-model="name">
      </p>
      <p>
        <span>手机号</span>
        <input style="height:88%" type="text" placeholder="收入手机号码" v-model="phone">
      </p>
    </div>
    <p class="personal1">
      <span>我的地址</span>
    </p>
    <div class="id">
      <span>详细地址</span>
      <textarea style="font-size:0.3rem" cols="30" rows="3" placeholder="输入详细地址" v-model="text"></textarea>
    </div>
    <button @click="ok()">确定修改</button>
  </div>
</template>
<script>
export default {
  data() {
    return {
      name: "",
      phone: "",
      text: ""
    };
  },
  mounted() {
    this.$store.commit("headerTab", true);
    this.$store.commit("footerTab", false);
    this.$store.commit("header", "个人资料");
    this.$store.commit("fanhui", true);
  },
  methods: {
    ok() {
      console.log("地址");
    }
  }
};
</script>
<style scoped="">
.div {
  padding-top: 0.88rem;
  min-height: 100%;
  background: #f5f5f5;
}
.personal {
  height: 0.8rem;
  padding-left: 0.3rem;
  line-height: 0.8rem;
  font-size: 0.3rem;
  color: #1e853c;
  background: #fff;
}
.personal > span {
  border-left: 2px solid #1e853c;
  padding-left: 0.2rem;
}
.xx {
  width: 100%;
  margin-top: 0.12rem;
  font-size: 0.3rem;
}
.xx span {
  color: #1e853c;
  display: inline-block;
  width: 1.84rem;
}
.xx p {
  height: 0.8rem;
  border-bottom: 2px solid #f5f5f5;
  background: #fff;
  line-height: 0.8rem;
  padding-left: 0.3rem;
}
.personal1 {
  height: 0.8rem;
  padding-left: 0.3rem;
  line-height: 0.8rem;
  font-size: 0.3rem;
  color: #1e853c;
  background: #fff;
  margin-top: 0.2rem;
}
.personal1 > span {
  border-left: 2px solid #1e853c;
  padding-left: 0.2rem;
}
.id {
  height: 1.62rem;
  background: #fff;
  margin-top: 0.1rem;
  padding-top: 0.26rem;
  padding-left: 0.3rem;
}
.id > span {
  color: #1e853c;
  /* padding-left: 0.3rem; */
  font-size: 0.3rem;
  display: inline-block;
  width: 1.84rem;
  float: left;
}
button {
  width: 86%;
  height: 0.8rem;
  background: #1e853c;
  margin-top: 0.4rem;
  margin-left: 7%;
  border-radius: 0.4rem;
  color: #fff;
  margin-bottom: 2rem;
}
</style>
