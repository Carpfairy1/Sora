<template>
    <div class="content-wrapper">
        <div id="slide-caption" class="slide-caption"><div id="introduce" class="introduce"  :class="{ animated: isMounted }">使用文本创造视频</div>
        <div id="fubiaoti" class="fubiaoti"  :class="{ animated: isMounted }">采用最先进的人工智能模型，可以根据文本指令创建现实和想象的场景。</div>
        <router-link to="/sora" class="try"  :class="{ animated: isMounted }">马上体验</router-link> </div>
              
    </div>
</template>
<script>
export default {
      name: 'HomePage',
      data(){
        return{
            isMounted: false,
        }
    
      },
      mounted() {
    // 在组件挂载完成后设置isMounted为true触发动画
    this.$nextTick(() => {
      this.isMounted = true;
    });
  },
    }
</script>
<style scoped>
.slide-caption{
    position: absolute;
    z-index: 70;
    color: var(--text-color-lightest);
    left: 12.6563vw;
    top: 15.4583vw;
    max-width: 60vw;
}
.introduce{
    position: absolute;
    width: 700px;
    color: white;
    font-size: 2.9167vw;
    font-weight: 600;
}
.fubiaoti{
    position: absolute;
    top: 12vh;
    width: 700px;
    color: white;
    font-size: 1.4167vw;
    font-weight: 600;
}
.try{
    position: absolute;
    background-color: #F42267;
    text-align: center;
    width: 8vw;
    height: 5vh;
    line-height: 4.5vh;
    top: 25vh;
    color: white;
    cursor: pointer;
    font-size: 15px;
    font-weight: 600;
    border-radius: 20px;
    transition: 0.5s;


}
.try:hover{
    background-color: transparent;
    border: 1px solid #F42267;
    transition: 0.5s;
}
@keyframes slideUp {
  from {
    transform: translateY(50%);
    opacity: 0;
  }
  to {
    transform: translateY(0);
    opacity: 1;
  }
}

.animated {
  animation: slideUp 1.5s ease forwards;
}
</style>
