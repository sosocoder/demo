<template>
  <div class="home">
    <div class="box" id="box" >
      <div class="imgBox" v-for="(item,index) in imglists" :key="index" @mouseover='todo(item)' @mouseout='todo1(item)'>
        <img :src='item.url'>
        <div class="info" v-show="item.flag">
          <span>{{item.title}}</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>


export default {
  data() {
    return {
      imglists:[
      {url:require("../imgs/1.jpg"),title:'图片一',flag:false},
      {url:require("../imgs/2.jpg"),title:'图片二',flag:false},
      {url:require("../imgs/3.jpg"),title:'图片三',flag:false},
      {url:require("../imgs/4.jpg"),title:'图片四',flag:false},
      {url:require("../imgs/5.jpg"),title:'图片五',flag:false},
      {url:require("../imgs/6.jpg"),title:'图片六',flag:false},
      {url:require("../imgs/7.jpg"),title:'图片四',flag:false},
      {url:require("../imgs/8.jpg"),title:'图片五',flag:false},
      {url:require("../imgs/9.jpg"),title:'图片六',flag:false},
      {url:require("../imgs/5.jpg"),title:'图片五',flag:false},
      {url:require("../imgs/6.jpg"),title:'图片六',flag:false},
      {url:require("../imgs/7.jpg"),title:'图片四',flag:false},
      {url:require("../imgs/8.jpg"),title:'图片五',flag:false},
      {url:require("../imgs/9.jpg"),title:'图片六',flag:false},
      ]
    };
  },
  methods:{
    todo(i){
      i.flag = !i.flag
    },
    todo1(i){
      i.flag = !i.flag
    }
  }
};
</script>
<style scoped>
* {
  margin: 0;
  padding: 0;
}
.box {
  width: 1500px;
  margin: 0 auto;
  display: flex;
  flex-wrap: wrap;
}
.box:after {
  /* 处理不能填充满一行的空白区域不被已有图片平分*/
  content: "";
  flex-grow: 99999;
}
.imgBox {
  flex-grow: 1;
  margin: 5px;
  position: relative;
  /* overflow: hidden; */
   
}
.imgBox:hover .info{
  opacity: 1;
}
.imgBox .info{
  width: 100%;
  height: 100%;
  position: absolute;
  bottom: 5px;
  opacity: 0;
  transition: all 0.3s linear;
}
.imgBox .info:hover{
  opacity: 0.8;
  transform: translateX(40%);
}
.imgBox .info span{
  font-weight: bolder;
  color: #fff;
  position: absolute;
  bottom: 0;
  display: block;
}
.imgBox img {
  width: auto;
  height: 150px;
  object-fit: cover;
  min-width: 100%;
}
</style>
