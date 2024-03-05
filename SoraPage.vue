
<template>
    <div>
      <!-- Your content goes here -->
      <div class="gen_video" v-if="gening==false">
        <div class="title">
          <div class="model_name" @click="generateVideo" :class="{ active: currentTab === 'ttv' }">文本生成视频</div>
          <div class="model_name2" @click="generateImage" :class="{ active: currentTab === 'ttp' }">文本生成图片</div>

        </div>
        
        <div class="switch_ttv" v-if="generatorType === 'video'">
          <textarea name="" id="" cols="30" rows="10" class="prompt" placeholder="使用一段语言描述你想生成的视频内容"></textarea>
        <div class="param">
          <div class="btn"></div>
          <div class="pre" @click="create">来个创意</div>
          <div class="gen" @click="gen_sora">生成视频</div>

        </div>
        </div>
        <div class="switch_ttp" v-if="generatorType === 'image'">
          <textarea name="" id="" cols="30" rows="10" class="prompt" placeholder="使用一段提示词描述你想生成的图片内容"></textarea>
        <div class="param">
          <div class="btn"></div>
          <div class="pre">来个创意</div>
          <div class="gen">生成图片</div>
        </div>
        </div>

      </div>
      <div class="gening" v-if="gening==true">
        <div class="loading-container">
        <div class="loading-spinner"></div>
        <div class="loading-text" :style="{ opacity: textOpacity }">Loading<span class="ellipsis">...</span></div>
      </div>
      </div>
      <!-- <div class="slogn">copyright 2024</div> -->
    </div>
  </template>
<script>
export default {
      name: 'SoraPage',
      data(){
        return{
          generatorType: 'video',
          currentTab: 'ttv',
          gening:false,
          textOpacity: 0
        }
      },
      methods: {
        generateVideo() {
          this.generatorType='video'
          // 触发视频生成逻辑
          this.currentTab='ttv'

        },
        generateImage() {
          this.generatorType='image'
          this.currentTab='ttp'
          // 触发图片生成逻辑
     
    },
      create(){
            alert('请求生成创意接口')
            },
      gen_sora(){
        this.gening=true
      },
      
            
    },
    mounted() {
    setTimeout(() => {
      this.textOpacity = 1; // 设置文本透明度为1，实现渐出效果
    }, 100); // 设置一个延迟以确保加载动画首先出现
  }
      
    }
</script>
<style scoped>
.gen_video{
  position: absolute;
  top: 45%;
  left: 50%;
  transform: translate(-50%,-50%);
  width: 60vw;
  height: 35vh;
  background-color: #1D1E23;
  border-radius: 10px;
}
.title{
  position: absolute;
  width:60vw ;
  height: 5vh;
  border-bottom: 1px solid #3D3F4D;

}
.model_name{
  position: absolute;
  bottom: 0vh;
  left: 1vw;
  color: rgb(202, 202, 202);
  font-weight: 600;
  border-bottom: 3px solid transparent;
  padding-bottom: 1vh;
  cursor: pointer;
}
.model_name2{
  position: absolute;
  bottom: 0vh;
  left: 8vw;
  color: rgb(202, 202, 202);
  font-weight: 600;
  border-bottom: 3px solid transparent;
  padding-bottom: 1vh;
  cursor: pointer;

}
.prompt{
  position: absolute;
  font-size: 15px;
  font-weight: 600;
  left: 1vw;
  resize:none;
  background-color: #1D1E23;
  width: 58vw;
  border:none;
  color:rgb(202, 202, 202) ;
  /* left: 50%; */
  top: 8vh;
}
.prompt:focus{
  outline: none;
}
.param{
  position: absolute;
  bottom: 0;
  width:60vw ;
  height: 10vh;
  /* background-color: white; */
}
.btn{
  position: absolute;
  top: 0;
  left: 1vw;
  background-image: url('@/assets/options.png');
  width: 1.5vw;
  height: 1.5vw;
  background-size: cover;
  cursor: pointer;
  /* border:1px solid gray; */
  /* background-color:#F42267; */
  /* z-index: 100; */
}
.gen{
  position: absolute;
  color: #6c6D82;
  font-weight: 600;
  left: 52vw;
  background-color: black;
  padding:1vh 1vw ;
  transition: 0.5s;
  cursor: pointer;
  border-radius: 5px;
}
.gen:hover{
  background-color: transparent;
  border: 1px solid black;
  /* color:rgb(202, 202, 202) ; */
  transition: 0.5s;

}
.pre{
  position: absolute;
  color: #6c6D82;
  font-weight: 600;
  left: 45vw;
  background-color: black;
  padding:1vh 1vw ;
  transition: 0.5s;
  cursor: pointer;
  border-radius: 5px;
}
.pre:hover{
  background-color: transparent;
  border: 1px solid black;
  /* color:rgb(202, 202, 202) ; */
  transition: 0.5s;
}
.slogn{
  position: absolute;
  bottom: 2vh;
  color: white;
}
.active{
  border-bottom: 3px solid #F42267;
}
.gening{
  position: absolute;
  top: 45%;
  left: 50%;
  transform: translate(-50%,-50%);
  width: 50vw;
  height: 60vh;
  background-color: #1D1E23;
  border-radius: 10px;
}
.loading-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100%;
}

.loading-spinner {
  border: 4px solid rgba(0, 0, 0, 0.1);
  border-left-color: #e4e4e4;
  border-radius: 50%;
  width: 50px;
  height: 50px;
  animation: spin 1s linear infinite;
}

@keyframes spin {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}

.ellipsis {
  overflow: hidden;
  position: relative;
  width: 0.5em;
  text-align: center;
}

.ellipsis::after {
  content: '...';
  position: absolute;
  width: 1em;
  height: 1em;
  top: 0;
  left: 0;
  animation: ellipsis 1s infinite;
}

.loading-text {
  margin-top: 20px;
  display: flex;
  align-items: center;
  transition: opacity 0.5s ease; /* 添加渐出效果的过渡 */
}
@keyframes ellipsis {
  0% {
    width: 0.5em;
  }
  50% {
    width: 1em;
  }
  100% {
    width: 0.5em;
  }
}
</style>