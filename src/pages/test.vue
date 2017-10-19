<template>
  <div class="big" @click="click">
    <div id="test" class="popup">
      <div class="content">
        this tip content
      </div>
      <div class="tiptri"></div>
    </div>
  </div>
</template>
<style>
  .big{
    width:100%;
    height: 100%;
   /* background-color: #b0b0b0;*/
  }
  .popup
  {
    position: relative;
    float: left;
    overflow: hidden;
    box-sizing: border-box;
  }
  .popup div{
    overflow: hidden;
    box-sizing: border-box;
  }
  .content{
    box-shadow:0px 0px 10px 0px #9b9b9b;
    border-radius: 3px;
    background: #e2e2e2;
    font-size: 1.2em;
    height: 1.2em;
    white-space: nowrap;
    margin-bottom: 16px;
  }
  .tiptri
  {
    position: absolute;
    bottom: 0;
    left: calc(50% - 16px);
    width: 0;
    height: 0;
    border-left:8px solid transparent;
    border-right:8px solid transparent;
    border-top:16px solid #e2e2e2;
  }
  @keyframes closepop
  {
    from {height:0;}
    to{height: 1.2em}
  }
</style>
<script>
  export default{
      data(){return{}},
    methods:
      {
          click()
          {
              var element=document.getElementById('test');
            CopyAtts(element.style,{animation:'closepop 0.5s',height:'auto'});
          }
      }
  }
  /**
   * 复制属性到目标对象
   * @param {object} to 目标对象
   * @param {object} from 源对象
   * @returns {object} 返回属性添加后的目标对象
   */
  function CopyAtts(to,from) {
    for(var key in from){
      to[key]=from[key];
    }
    return to;
  }
</script>
