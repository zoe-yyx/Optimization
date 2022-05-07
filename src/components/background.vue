
<template>
    <kinesis-container class="header">
    <!-- 圆圈 start -->
      <kinesis-element v-for="item in circleDataList" :key="item" :class="`circle circle-${item}`" 
      :strength="40" type='translate' axis="x" transformOrigin='center' tag='div'>
      </kinesis-element>
      <!-- 圆圈 end -->

      <!-- 大标题 start -->
        <h1>
          <kinesis-element class="title" :originY="10" type="depth" transformOrigin='center 100px' tag="div">hello</kinesis-element>
        </h1>
        <!-- 大标题 end -->

        <!-- 副标题 start -->
        <kinesis-element class="catcher" :originY="10" type="depth" transformOrigin='center 400px' tag="div"> 现代前端应用开发实践（2022春季） </kinesis-element>
        <kinesis-element class="catcher" :originY="20" type="depth" transformOrigin='center 400px' tag="div"> 第七课作业 </kinesis-element>
        <kinesis-element class="catcher" :originY="30" type="depth" transformOrigin='center 400px' tag="div"> 前端性能优化 </kinesis-element>
        <!-- 副标题 end -->

        <!-- 可点击icon start -->
        <kinesis-element class="catcher github"  type="depth" transformOrigin='center 200px' tag="div"> 
          <a href="https://github.com/zoe-yyx/Optimization" target="_blank">
          <img src="https://aminerman.com/kinesis/img/github.0c83fd0d.svg" height="30" alt=""></a>
        </kinesis-element>
        <!-- 可点击icon end -->

    <div class="intro">
        <div class="container">
            <h2 class="center">本作业中用到的优化方法 / Optimization Methods </h2>
            <p class="code"> 
              <span class="vue">从采用工具方面</span>可以分为3点 <br/> 
              <span>NO.1：</span>使用构建工具Vite代替传统构建工具的不足之处。<br/>
              <span>NO.2：</span>使用了Vue3，在编译阶段Vue3在diff算法优化、静态提升、预字符串化、缓存事件处理函数、SSR方面都做了进一步优化，并用到transform等图形、动画优化方法<br/>
              <span>NO.3：</span>引用了视觉运动 (vue-kinesis)库。
              </p>
          </div>
      </div>

    </kinesis-container>



</template>
<script>
export default {
setup() {
let circleDataList = ["blue","purple","yellow","green","orange","red"];
// let titleList = ['k','i','n','e','s','i','s'];
let titleList = [{key:'k',type:'rotate'},{key:'i',type:'translate'} , {key:'n',type:'rotate'}, {key:'e',type:'translate'}, {key:'s',type:'translate'}, {key:'i',type:'rotate'}, {key:'s',type:'translate'}];

let topAry = ['-20px','-7px' , '8px', '13px', '-5px', '0px'];
 const setMarginTopValue = (index,titleList)=>{
   let ind=index
    if(index===0 || index===titleList?.length-1){
      return '0px';
    }else {
      return topAry[titleList?.length%ind];
    }
  }
   return {
      setMarginTopValue,
      circleDataList,
      titleList
    }
 } 
}
</script>


<style scoped>
  .header{
      display: -webkit-box;
      display: -ms-flexbox;
      display: flex;
      -webkit-box-orient: vertical;
      -webkit-box-direction: normal;
      -ms-flex-direction: column;
      flex-direction: column;
      -webkit-box-pack: center;
      -ms-flex-pack: center;
      justify-content: center;
      -webkit-box-align: center;
      -ms-flex-align: center;
      align-items: center;
      height: 90vh;
      position: relative;
  }
  .circle.circle-blue {
      background-color: #eaf1fa;
      width: 32vw;
      height: 32vw;
      top: 5%;
      right: -16vw;
  }
  .circle.circle-purple {
      border: 25px solid #f2eafa;
      width: 16vw;
      height: 16vw;
      left: 50%;
  }
  .circle.circle-yellow {
      background-color: #faf9ea;
      width: 8vw;
      height: 8vw;
      left: 30%;
      top: 25%;
  }
  .circle.circle-green {
      background-color: #eafaf2;
      width: 10vw;
      height: 10vw;
      right: 20%;
      top: 90%;
  }
  .circle.circle-orange{
      border: 25px solid #faf3ea;
      width: 8vw;
      height: 8vw;
      left: 20%;
      top: 60%;
  }
  .circle.circle-red {
      background-color: #faeaea;
      width: 12vw;
      height: 12vw;
      left: -4.8vw;
      top: 25%;
  }
  .circle {
      border-radius: 100%;
      position: absolute;
  }

  .header h1 {
    position: relative;
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    color: #351b1b;
    font-size: 72px;
  }

  .header .catcher {
    position: relative;
    z-index: 5;
  }
   .header .github {
    margin-top: 20px;
  }

  .intro {
    margin-top: 130px;
  }
  .container {
    width: 800px;
    max-width: 90%;
    margin: 0 auto;
  }
  .center {
    text-align: center;
  }
  h2 {
    font-size: 25px;
    margin-top: 30px;
  }
  .code {
    background-color: #eaf1fa;
    padding: 10px 20px;
    border-radius: 10px;
    margin: 0 auto;
    margin-top: 30px;
    max-width: 600px;
    line-height: 1.5;
  }
  .vue {
    color: #19ad9b;
  }
  .container span {
    font-weight: 700;
  }
</style>
