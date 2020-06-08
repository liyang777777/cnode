<template>
  <div>
    <div class="conter">
      <!-- 头部: 导航栏 -->
      <div class="nav">
        <div class="img">
          <img src="https://static2.cnodejs.org/public/images/cnodejs_light.svg" alt="cnode" />
        </div>
        <div class="box">
          <input type="text" />
        </div>
        <div class="btn">
          <div class="btn1">首页</div>
          <div class="btn2">新手入门</div>
          <div class="btn3">API</div>
          <div class="btn4">关于</div>
          <div class="btn5">注册</div>
          <div class="btn6">登录</div>
        </div>
      </div>

      <!-- 中间部分 -->
      <div class="content">
        <div class="content1">全部</div>
        <div class="content2">精华</div>
        <div class="content3">分享</div>
        <div class="content4">问答</div>
        <div class="content5">招聘</div>
        <div class="content6">客户端测试</div>
        <div class="content7">
          <div v-for="(item,index) in arr" :key="index">
            <div @click="goTo(item)">{{item.title}}</div>
          </div>
        </div>
        <el-pagination
          @size-change="handleSizeChange"
          @current-change="handleCurrentChange"
          :current-page="currentPage"
          :page-sizes="[10, 20, 30, 40]"
          :page-size="10"
          layout="total, sizes, prev, pager, next, jumper"
          :total="40"
        ></el-pagination>
      </div>
      <!-- 侧边框 -->
      <div class="im">
        <div class="im1">
          <img src="../assets/QQ图片20200605161515.png" alt="cnode" />
        </div>
        <div class="im2">
          <img src="../assets/QQ图片20200605161559.png" alt="cnode" />
        </div>
        <div class="im3">
          <img src="../assets/QQ图片20200605161628.png" alt="cnode" />
        </div>
        <div class="im4">
          <img src="../assets/QQ图片20200605161655.png" alt="cnode" />
        </div>
        <div class="im5">
          <img src="../assets/QQ图片20200605161718.png" alt="cnode" />
        </div>
        <div class="im6">
          <img src="../assets/QQ图片20200605161739.png" alt="cnode" />
        </div>
      </div>
      <!-- 底部 -->
      <div>
        <div class="button">
          <img src="../assets/QQ图片20200605170839.png" alt />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "Home",
  props: {},
  components: {},
  data() {
    return {
      arr: [],
      //默认是第几页
      currentPage: 1,
      //默认一页多少条
      pageSize: 10
    };
  },
  methods: {
    getData() {
      axios
        .get("https://cnodejs.org/api/v1/topics")
        .then(res => {
          this.arr = res.data.data;
          console.log(res);
        })
        .catch(err => {
          console.log(err);
        });
    },
    handleSizeChange(val) {
      this.pageSize = val
    },
    handleCurrentChange(val) {
      this.currentPage = val
    },
    goTo(item) {
      this.$router.push({name: 'detail', query: {id: item.id}})
    }
  },
  mounted() {
    this.getData();
  },
  watch: {},
  computed: {}
};
</script>

<style scoped lang='scss'>
* {
  margin: 0;
  padding: 0;
}
.nav {
  width: 1400px;
  height: 50px;
  background-color: rgb(68, 68, 68);
  display: flex;
  position: relative;
}
.img {
  width: 200px;
  height: 200px;
  margin-left: 100px;
}
.box {
  width: 245px;
  height: 50px;
  display: flex;
  margin-left: 50px;
}
.btn {
  width: 365px;
  height: 50px;
}
.btn:hover {
  background-color: rgb(68, 68, 68);
  color: aliceblue;
}
.btn1 {
  width: 50px;
  height: 50px;
  display: flex;
  margin-left: 320px;
  margin-top: 15px;
  position: absolute;
}
.btn2 {
  width: 70px;
  height: 50px;
  display: flex;
  margin-left: 385px;
  margin-top: 15px;
  position: absolute;
}
.btn3 {
  width: 50px;
  height: 50px;
  display: flex;
  margin-left: 480px;
  margin-top: 15px;
  position: absolute;
}
.btn4 {
  width: 50px;
  height: 50px;
  display: flex;
  margin-left: 540px;
  margin-top: 15px;
  position: absolute;
}
.btn5 {
  width: 50px;
  height: 50px;
  display: flex;
  margin-left: 600px;
  margin-top: 15px;
  position: absolute;
}
.btn6 {
  width: 50px;
  height: 50px;
  display: flex;
  margin-left: 660px;
  margin-top: 15px;
  position: absolute;
}
.content {
  width: 906px;
  height: 40px;
  background-color: rgb(246, 246, 246);
  display: flex;
  position: relative;
  left: 100px;
  top: 50px;
}
.content:hover {
  background-color: rgb(128, 189, 1);
  color: blue;
}
.content1 {
  width: 50px;
  height: 40px;
  display: flex;
  font-size: 25px;
  background: lawngreen;
  margin-left: 50px;
}
.content2 {
  width: 50px;
  height: 40px;
  display: flex;
  background: lawngreen;
  margin-left: 50px;
  font-size: 25px;
}
.content3 {
  width: 50px;
  height: 40px;
  display: flex;
  background: lawngreen;
  margin-left: 50px;
  font-size: 25px;
}
.content4 {
  width: 50px;
  height: 40px;
  display: flex;
  background: lawngreen;
  margin-left: 50px;
  font-size: 25px;
}
.content5 {
  width: 50px;
  height: 40px;
  display: flex;
  background: lawngreen;
  margin-left: 50px;
  font-size: 25px;
}
.content6 {
  width: 130px;
  height: 40px;
  display: flex;
  background: lawngreen;
  margin-left: 50px;
  font-size: 25px;
}

.u1 {
  width: 35px;
  height: 35px;
}
.time {
  margin-left: 1100px;
}
.im {
  display: flex;
  position: relative;
}
.im1 {
  width: 350px;
  height: 150px;
  display: flex;
  position: absolute;
  left: 1111px;
  top: 10px;
}
.im2 {
  width: 350px;
  height: 150px;
  display: flex;
  position: absolute;
  left: 1111px;
  top: 180px;
}
.im3 {
  width: 350px;
  height: 150px;
  display: flex;
  position: absolute;
  left: 1111px;
  top: 360px;
}
.im4 {
  width: 350px;
  height: 150px;
  display: flex;
  position: absolute;
  left: 1111px;
  top: 540px;
}
.im5 {
  width: 350px;
  height: 150px;
  display: flex;
  position: absolute;
  left: 1111px;
  top: 730px;
}
.im6 {
  width: 350px;
  height: 150px;
  display: flex;
  position: absolute;
  left: 1111px;
  top: 900px;
}
.button {
  width: 1080px;
  height: 160px;
  background: rgb(246, 246, 246);
  display: flex;
  position: absolute;
  top: 1170px;
  left: 100px;
}
</style>