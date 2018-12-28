<template>
  <div class="tijao">
    <p class="personal">
      <span>提交任务</span>
    </p>
    <div class="photo">
      <p>上传图片</p>
      <div class="photo1">
        <div style="margin-left:0.2rem">
          <img src="../../assets/img/vip.png" alt>
        </div>
      </div>
      <van-uploader class="photo2" :after-read="onRead" accept="image/gif, image/jpeg" multiple>
        <van-icon class="icon" name="plus"/>
      </van-uploader>
    </div>
    <p class="Taskhallap">
      <span>任务规则</span>
    </p>
    <div class="Taskhallapd">
      <p style="padding-top:0.2rem">1.会员每天可领取2条朋友圈发布任务</p>
      <p>2.发布朋友圈的时长不低于3小时</p>
      <p>3.发布任务是必须与平台内的文案、图片一致</p>
      <p>4.不得屏蔽微信好友查看您的朋友圈</p>
      <p>5.上传的图片必须输朋友圈的全屏截图</p>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      msg: "提交任务详情"
    };
  },
  mounted() {
    this.$store.commit("headerTab", true);
    this.$store.commit("footerTab", false);
    this.$store.commit("header", "提交任务详情");
    this.$store.commit("fanhui", true);
  },
  methods: {
    onRead(file) {
      console.log(file);
    }
  }
};
</script>
<style scoped>
.tijao {
  min-height: 100%;
  padding-top: 0.88rem;
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
.photo {
  margin-top: 0.1rem;
  min-height: 2.3rem;
  background: #fff;
  padding-left: 0.3rem;
  padding-top: 0.24rem;
  overflow: hidden;
}
.photo > p {
  color: #1e853c;
  font-size: 0.3rem;
  margin-bottom: 0.26rem;
}
.photo1 > div {
  height: 1.2rem;
  width: 1.2rem;
  border-radius: 5px;
  border: 1px solid #999;
  overflow: hidden;
  float: left;
  margin-top: 0.1rem;
}
.photo1 > div > img {
  height: 100%;
  width: 100%;
}
.photo2 {
  height: 1.2rem;
  width: 1.2rem;
  text-align: center;
  border: 1px solid #999;
  float: left;
  /* margin-top: 0.26rem; */
  border-radius: 4px;
  margin-left: 0.3rem;
  margin-top: 0.1rem;
}
.icon {
  color: #999;
  font-size: 0.7rem;
  line-height: 1.2rem;
}
.Taskhallapd {
  padding-left: 0.3rem;
  background: #fff;
}
.Taskhallapd > p {
  font-size: 0.3rem;
  color: #1e853c;
  padding-bottom: 0.26rem;
}
.delate {
  border: 1px solid #999;
  width: 1rem;
  text-align: center;
  color: #999;
  border-radius: 4px;
  float: right;
  margin-bottom: 0.2rem;
}
.Taskhallap {
  margin-top: 0.4rem;
  height: 0.8rem;
  line-height: 0.8rem;
  padding-left: 0.3rem;
  background: #fff;
  font-size: 0.3rem;
  color: #1e853c;
  margin-bottom: 0.1rem;
}
.Taskhallap > span {
  display: inline-block;
  padding-left: 0.14rem;
  height: 0.4rem;
  border-left: 3px solid #1e853c;
  line-height: 0.4rem;
}
</style>
