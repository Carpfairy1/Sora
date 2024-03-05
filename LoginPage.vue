
<template>
    <div class="login-page">
        <div class="show"> 
            <div class="title">AI尽此时,All for AI</div>
            <div class="desc">一站式AI效率工具，娱乐，游戏，咨询，应用中心,超过千种AI人物角色，百种AI创作工具，娱乐与科技前沿论坛</div>
            <div class="border"><div class="pic"></div>
            </div>
        </div>
        <div class="login">
            <div class="tips">欢迎来到Compaion AI</div>
            <div class="tips2">没有账号？<router-link to="/sign" class="sign">免费注册</router-link></div>
            <input type="text" class="account" v-model="account" placeholder="Username or Email">
            <input type="password" class="key" v-model="keyword" placeholder="Password">
            <div class="loginbtn">登录</div>
            <div class="forget">忘记密码？</div>
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
        account: '' ,
      keyword:''// 设置默认值为 '默认值'
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
  .account{
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
  .account:focus{
    outline: #F42267 1px solid;
    font-family: Roobert,Inter,system-ui;
  }
  .key{
    position: absolute;
    top: 42%;
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
  .loginbtn{
    position: absolute;
    top: 57%;
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
  .forget{
    position: absolute;
    top: 64%;
    left: 50%;
    color: rgb(80, 80, 80);
    transform: translate(-50%);
    font-size: 0.6vw;
    font-weight: 500;
    cursor: pointer;
  }
  .forget:hover{
    color: #F42267;

  }
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


  </style>
  