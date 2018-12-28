<template>
  <div class="card">
    <div v-for="item in list" :key="item.id">
      <div class="cred">
        <p>{{ item.name }}</p>
        <p>持卡人 ：{{ item.nicknaem }}</p>
        <p>{{ item.code }}</p>
        <div class="anniu">
          <button
            class="xuanz"
            :class="{size:item.id==item.uid}"
            @click="xuanz(item.id,item.uid)"
          >选择</button>
          <br>
          <button class="delate" @click="delate(item.id)">删除</button>
        </div>
      </div>
    </div>
    <div class="diaj" @click="add()">
      <img src="../../assets/img/yinhang.png" alt>
      <span>添加银行卡</span>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      msg: "英航卡",
      list: [
        {
          id: "1",
          name: "中国银行",
          nicknaem: "世界",
          code: "2342342342342343543",
          uid: "2"
        },
        {
          id: "2",
          name: "中国银行",
          nicknaem: "世界",
          code: "2342342342342343543",
          uid: "2"
        },
        {
          id: "3",
          name: "中国银行",
          nicknaem: "世界",
          code: "2342342342342343543",
          uid: "2"
        }
      ],
      count: 0
    };
  },
  mounted() {
    this.$store.commit("headerTab", true);
    this.$store.commit("footerTab", false);
    this.$store.commit("header", "添加银行卡");
    this.$store.commit("fanhui", true);
  },
  methods: {
    //   删除英航卡
    delate(id) {
      console.log(id);
    },
    // 选择默认的英航卡
    xuanz(id, uid) {
      this.count++;
      //   console.log(id, uid);
      if (this.count == 1) {
        if (id == uid) {
          this.$toasted.error("不能重复选择").goAway(1200);
        } else {
          this.$toasted.success("操作成功").goAway(1200);
        }
      } else {
        this.$toasted.error("不能频繁操作").goAway(1200);
        setTimeout(() => {
          this.count = 0;
        }, 3000);
      }
    },
    // 添加银行卡的操作
    add() {
      this.$router.push("/addcard");
    }
  }
};
</script>
<style scoped>
.card {
  min-height: 100%;
  background: #f5f5f5;
  padding-top: 0.88rem;
}
.cred {
  width: 92%;
  height: 1.86rem;
  margin-left: 4%;
  background: #fff;
  margin-top: 0.3rem;
  border-radius: 4px;
  padding-top: 0.3rem;
  padding-left: 0.3rem;
  padding-right: 0.24rem;
  position: relative;
}
.cred > p {
  height: 0.5rem;
  font-size: 0.3rem;
  width: 70%;
  float: left;
}
.anniu {
  height: 100%;
  width: 30%;
  text-align: center;
  position: absolute;
  top: 0.2rem;
  right: 0;
}
.anniu > button {
  width: 1rem;
  height: 0.4rem;
  background: none;
  line-height: 0.4rem;
}
.delate {
  border: 1px solid #cccccc;
  border-radius: 4px;
  margin-top: 0.2rem;
  color: #ccc;
}
.xuanz {
  border: 1px solid #1e853c;
  border-radius: 4px;
  color: #1e853c;
}
.size {
  border: 1px solid #cccccc;
  border-radius: 4px;
  margin-top: 0.2rem;
  color: #d2d2d2;
}
.diaj {
  background: #1e853c;
  position: relative;
  top: 0.44rem;
  width: 86%;
  height: 0.8rem;
  margin: 0 auto;
  border-radius: 0.5rem;
  color: #fff;
}
.diaj > img {
  height: 0.46rem;
  width: 0.52rem;
  float: left;
  margin-left: 0.3rem;
  margin-top: 0.18rem;
}
.diaj > span {
  font-size: 0.3rem;
  margin-left: 0.32rem;
  line-height: 0.8rem;
}
</style>
