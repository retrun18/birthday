<template>
  <div class="big" @click="click">
    <div id="TipPopup" class="popup">
      <div class="tipcontent">
        this tip content
      </div>
      <div class="tiparrow"></div>
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
    box-sizing: border-box;
  }
  .popup div{
    box-sizing: border-box;
  }
  .tipcontent{
    box-shadow:0px 0px 10px 0px #754413;
    border-radius: 3px;
    background: #e2e2e2;
    font-size: 1.2em;
    height: 1.2em;
    white-space: nowrap;
    margin-bottom: 12px;
    background-image: -webkit-gradient( linear, left bottom, left top, color-stop(0, rgb(131, 154, 202)), color-stop(1, rgb(158, 194, 229)) );
  background-image: -webkit-linear-gradient(bottom, rgb(131, 154, 202) 0%, rgb(158, 194, 229) 100%);
    background-image: linear-gradient(bottom, rgb(131, 154, 202) 0%, rgb(158, 194, 229) 100%);

  }
  .tiparrow
  {position: absolute;
    bottom: 0;
    left: calc(50% - 10px);
    width: 0;
    height: 0;
    border-left:10px solid transparent;
    border-right:10px solid transparent;
    border-top:12px solid  rgb(131, 154, 202);
  }
  @keyframes hidden
  {
    from {opacity:1;}
    to{opacity: 0}
  }
  @keyframes show
  {
    from {opacity:0;}
    to{opacity: 1;}
  }
</style>
<script>
  export default{
      data(){return{}},
    methods:
      {
          click()
          {
              var element=document.getElementById('TipPopup');
            CopyAtts(element.style,{animation:'show 0.5s forwards',height:'auto'});
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
