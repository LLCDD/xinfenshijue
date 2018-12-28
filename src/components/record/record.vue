<template>
  <div class="record">
    <p class="recordp">
      <span>输入金额</span>
      <input type="text" placeholder="输入所需提现金额" v-model="money">
    </p>
    <div class="sj">
      <span>温馨提示：</span>
      <br>
      <span class="spanr">提现必须为100的倍数提现</span>
      <br>
      <button @click="ok()">确认申请提现</button>
    </div>
    <p class="recordp1">
      <span>申请记录</span>
    </p>
    <table class="table">
      <tr style="height:0.8rem">
        <th class="thc">时间</th>
        <th class="thc">金额</th>
        <th class="thc">状态</th>
      </tr>
      <tr style="height:0.8rem;border:0" v-for="(item,index) in list" :key="index">
        <td style="color:#999">{{ item.timer }}</td>
        <td style="color:#000">{{ item.money }}</td>
        <td ref="tdc" v-if="item.state == 1">提交成功</td>
        <td ref="tdc" v-if="item.state == 2">提交失败</td>
        <td ref="tdc" v-if="item.state == 0">申请中</td>
      </tr>
    </table>
  </div>
</template>
<script>
export default {
  data() {
    return {
      msg: "提现记录",
      money: "",
      list: [
        {
          timer: "2018/12/20 14:40:00",
          money: "100",
          state: "1"
        },
        {
          timer: "2018/12/20 14:40:00",
          money: "100",
          state: "2"
        },
        {
          timer: "2018/12/20 14:40:00",
          money: "100",
          state: "0"
        }
      ]
    };
  },
  mounted() {
    this.$store.commit("headerTab", true);
    this.$store.commit("footerTab", false);
    this.$store.commit("header", "提现记录");
    this.$store.commit("fanhui", true);
    // 改变  状态的字体颜色
    for (var i = 0; i < this.$refs.tdc.length; i++) {
      if (this.$refs.tdc[i].innerHTML == "提交成功") {
        this.$refs.tdc[i].style.color = "#1e853c";
      } else if (this.$refs.tdc[i].innerHTML == "提交失败") {
        this.$refs.tdc[i].style.color = "#851e1e";
      } else {
        this.$refs.tdc[i].style.color = "#999";
      }
    }
  },
  methods: {
    ok() {
      console.log("ok");
      if (this.money == "") {
        this.$toasted.error("提现金额不能为空").goAway(1200);
      }
    }
  }
};
</script>
<style scoped>
.record {
  min-height: 100%;
  background: #f5f5f5;
  padding-top: 0.88rem;
}
.recordp {
  height: 0.8rem;
  background: #fff;
  font-size: 0.3rem;
  line-height: 0.8rem;
  padding-left: 0.3rem;
}
.recordp > span {
  color: #1e853c;
  display: inline-block;
  width: 1.82rem;
}
.sj {
  height: 2.4rem;
  padding-top: 0.2rem;
  padding-left: 0.3rem;
}
.sj > span {
  color: #851e1e;
  font-size: 0.24rem;
}
.spanr {
  display: inline-block;
  margin-top: 0.18rem;
  margin-bottom: 0.4rem;
}
button {
  width: 85%;
  height: 0.8rem;
  border-radius: 0.5rem;
  color: #fff;
  background: #1e853c;
  margin-left: 7%;
  font-size: 0.3rem;
}
.recordp1 {
  width: 100%;
  height: 0.8rem;
  background: #fff;
  padding-left: 0.3rem;
  color: #1e853c;
  font-size: 0.3rem;
  line-height: 0.8rem;
}
.recordp1 > span {
  padding-left: 0.2rem;
  height: 0.4rem;
  line-height: 0.4rem;
  border-left: 3px solid #1e853c;
}
.table {
  margin-top: 0.1rem;
  background: #fff;
  width: 100%;
}
.thc {
  color: #1e853c;
  font-size: 0.3rem;
}
table {
  border: 0;
}
th {
  border: 0;
  border-bottom: 2px solid #f5f5f5;
}
td {
  border: 0;
  border-bottom: 2px solid #f5f5f5;
}
</style>
