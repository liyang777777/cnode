<template>
 <div class="conter">
   <div class="box">
     <div class="box1">Node.js专业中文社区</div>
     <form action="" method="get">
       <input type="text" name="userid" placeholder="请输入账号">
       <input type="password" name="userpw" id="请输入密码">
       <button type="submit">登录</button>
     </form>
   </div>
 </div>
</template>

<script>
 export default {
   name: '',
   props: {
   },
   components: {

   },
   data () {
     return {

     }
   },
   methods: {

   },
   mounted() {

   },
   watch: {

   },
   computed: {

   }
 }
</script>

<style scoped lang='scss'>
* {
  margin: 0;
  padding: 0;
}
.conter {
  background: aliceblue;
  position: relative;
  left: 0;
  top: 50%;
  width: 100%;
  height: 400px;
  margin-top: -200px;
  overflow: hidden;
}
.box {
  max-width: 600px;
  height: 400px;
  padding: 80px;
  text-align: center;
  margin: 0 auto;
}
.box1 {
  font-size: 40px;
  font-weight: 300;
}
.from {
  padding: 20px 0;
}
.from input {
  border: 1px solid #fff;
  width: 220px;
  padding: 10px 15px;
  display: block;
  margin: 0 auto 10px auto;
  border-radius: 30px;
  font-size: 18px;
  font-weight: 300;
  text-align: center;
}
from button {
  background: white;
  border: 0;
  padding: 10px 15px;
  color: green;
  border-radius: 8px;
  width: 250px;
  font-size: 16px;
}
.from button:hover {
  background: rgb(209, 96, 96);
}
</style>