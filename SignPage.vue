
<template>
    <div class="login-page">
        <div class="show"> 
            <!-- <div class="title">AI尽此时</div> -->
            <div class="title">All for AI, All for Life</div>
            <div class="desc">一站式AI效率工具，娱乐，游戏，咨询，应用中心,超过千种AI人物角色，百种AI创作工具，娱乐与科技前沿论坛</div>
            <div class="border"><div class="pic"></div>
            </div>
        </div>
        <div class="login">
            <div class="tips">创建新账户</div>
            <div class="tips2">已有账号？<router-link to="/login" class="sign">立即登录</router-link></div>
            <input type="text" class="Email" v-model="Email" placeholder="邮箱">
            <input type="text" class="Username" v-model="Username" placeholder="账户名 （请勿使用特殊字符）">
            <input type="password" class="key" v-model="keyword" placeholder="密码（至少6位数）">
            <input type="password" class="rekey" v-model="rekeyword" placeholder="确认密码">
            <div class="safety"></div>

            <div class="signbtn">注册</div>
            <!-- <div class="forget">忘记密码？</div> -->
            <div class="icon-black"></div>
            <!-- <input type="k" class="account"> -->

        </div>
      <!-- Your login page content here -->
    </div>
  </template>
  
  <script>
  export default {
    name: 'LoginPage',
    data() {
    return {
        Email: '' ,
      keyword:'',
      Username:'',
      rekeyword:''// 设置默认值为 '默认值'
    };
  },
    beforeRouteEnter(to, from, next) {
      next(vm => {
        // Hide the header when entering the Login route
        vm.$parent.showHeader = false;
      });
    },
    beforeRouteLeave(to, from, next) {
      this.$parent.showHeader = true; // Ensure header is shown when leaving Login route
      next();
    },
  };
  </script>
  
  <style scoped>
  .login-page{
    width: 100vw;
    height: 100vh;
    background-color: white;
  }
  .show{
    position: absolute;
    width: 50vw;
    height: 100vh;
    background-color:#F42267;
  }
  .title{
    position: absolute;
    top: 10vh;
    left: 2vw;
    font-size: 65px;
    font-weight: bold;
    color: white;
    max-width: 40vw;
  }
  .desc{
    position: absolute;
    left: 2vw;
    color: white;
    font-size: 24px;
    top:12vw;
    max-width: 25vw;

  }
  .border{
    position: absolute;
    bottom: 0;
    right: 0;
    width: 40vw;
    height: 50vh;
    background-color: #282B2F;
    border-top-left-radius: 20px;
  }
  .pic{
    position: absolute;
    bottom: 0;
    right: 0;
    width: 39vw;
    height: 48vh;
    background-image: url('@/assets/show.png');
    background-size: cover;
  }
  .login{
    position: absolute;
    /* background-color:black; */
    top: 0;
    left: 0;
    /* transform: translate(-50%,-50%); */
    width: 50vw;
    height: 100vh;
    
  }
  .tips{
    position: absolute;
    top: 25%;
    left: 50%;
    transform: translate(-50%);
    font-size: 1.3vw;
    font-weight: 550;

  }
  .tips2{
    position: absolute;
    top: 30%;
    left: 50%;
    color: rgb(80, 80, 80);
    transform: translate(-50%);
    font-size: 0.6vw;
    font-weight: 500;
  }
  .sign{
    color:#F42267 ;
    margin-left: 0;
  }
  .Email{
    position: absolute;
    top: 35%;
    left: 50%;
    transform: translate(-50%);
    width: 18vw;
    height: 5vh;
    border: 1px solid #DFDFE4;
    border-radius: 5px;
    padding-left: 1vw;
  }
  input:focus{
    outline: #F42267 1px solid;
    font-family: Roobert,Inter,system-ui;
  }
  .Username{
    position: absolute;
    top:42%;
    left: 50%;
    transform: translate(-50%);
    width: 18vw;
    height: 5vh;
    border: 1px solid #DFDFE4;
    border-radius: 5px;
    padding-left: 1vw;

  }
  .Username:focus{
    outline: #F42267 1px solid;
    font-family: Roobert,Inter,system-ui;
  }
  .key{
    position: absolute;
    top: 49%;
    left: 50%;
    transform: translate(-50%);
    width: 18vw;
    height: 5vh;
    border: 1px solid #DFDFE4;
    border-radius: 5px;
    padding-left: 1vw;
  }
  .key:focus{
    outline: #F42267 1px solid;
    font-family: Roobert,Inter,system-ui;
  }
  .rekey{
    position: absolute;
    top: 56%;
    left: 50%;
    transform: translate(-50%);
    width: 18vw;
    height: 5vh;
    border: 1px solid #DFDFE4;
    border-radius: 5px;
    padding-left: 1vw;
  }
  .signbtn{
    position: absolute;
    top: 67%;
    left: 50%;
    transform: translate(-50%);
    width: 18vw;
    height: 5vh;
    /* border: 1px solid #DFDFE4; */
    border-radius: 5px;
    background-color: #F42267;
    text-align: center;
    border-radius: 15px;
    line-height: 5vh;
    color: white;
    font-weight: 600;
    cursor: pointer;
  }
  /* .forget{
    position: absolute;
    top: 7%;
    left: 50%;
    color: rgb(80, 80, 80);
    transform: translate(-50%);
    font-size: 0.6vw;
    font-weight: 500;
    cursor: pointer;
  }
  .forget:hover{
    color: #F42267;

  } */
  .icon-black{
    position: absolute;
    width: 191px;
  height: 30px;
  /* background-color: white; */
  /* height: 100%; */
  background-size: cover;
  background-image: url("@/assets/logo2.png");
  right: 2vw;
  bottom: 2vh;
  /* cursor: pointer; */
  }
  .safety{
    position: absolute;
    top: 63%;
    left: 50%;
    transform: translate(-50%);
    width: 18vw;
    height: 1vh;
    /* border: 1px solid #DFDFE4; */
    background-color: #DFDFE4;
    border-radius: 5px;
    padding-left: 1vw;
  }

  </style>
  