<template>
  <div class="teacher-abstract">
    <div class="teachers-materials">
      <img :src='thacherImg' alt="老师头像">
      <span class="teacher-name">李陶然</span>
      <span class="teacher-course-num">4</span>
      <span class="teacher-fans-num">986</span>
      <span class="teacher-course">课程</span>
      <span class="teacher-fan">粉丝</span>
      <span class="teacher-attention"><x-icon slot="icon" type="ios-heart" size="20"></x-icon><span>关注</span></span>
    </div>
    <div class=" teacher-introduction">
      <h4>教师简介</h4>
      <p>高级教师</p>
      <p class="p-one">six second  认证会员</p>
      <p>参加过国家级儿童心理健康实验研究</p>
    </div>
    <div class="teacher-course-list">
      <h4>课程</h4>
      <group>
        <panel :list='list'></panel>
      </group>
    </div>
  </div>
</template>

<script>
const list = [
  {
    src: "http://somedomain.somdomain/x.jpg",
    fallbackSrc: "http://placeholder.qiniudn.com/60x60/3cc51f/ffffff",
    title: "标题一",
    desc:'<span>主讲老师：</span><span class="teacher-name-font">李陶然</span>',
    url:'/courses-detail'
  }
];
import { Panel, Group } from "vux"
export default {
  name: "teacherAbstract",
  components: { Panel, Group },
  data() {
    return {
      thacherImg: "../../../build/logo.png",
      list
    };
  }
};
</script>

<style lang="less">
.teacher-abstract {
  margin-top: 10px;
  .teachers-materials {
    position: relative;
    margin-left: 6px;
    img {
      width: 70px;
      height: 70px;
      border: 1px solid transparent;
      border-radius: 50%;
    }
    .teacher-name {
      position: absolute;
      font-weight: bold;
      top: 0;
      left: 80px;
    }
    .teacher-course {
      position: absolute;
      top: 50px;
      left: 80px;
    }
    .teacher-course-num {
      position: absolute;
      font-weight: bold;
      top: 30px;
      left: 80px;
    }
    .teacher-fan {
      position: absolute;
      top: 50px;
      left: 130px;
    }
    .teacher-fans-num {
      position: absolute;
      font-weight: bold;
      top: 30px;
      left: 130px;
    }
    .teacher-attention {
      position: absolute;
      width: 70px;
      height:30px;
      border:1px solid orange;
      border-radius: 10%;
      align-items: center;
      bottom: 6px;
      right: 10px;

      color: orange;
    }
  }
  .teacher-introduction{
    margin-top: 20px;
    p{
         color: gray;
    }
    h4{
      margin: 6px 0;
    }
    .p-one{
      text-transform: capitalize;
    }
  }
  .teacher-course-list{
    position: relative;
    margin-top: 30px;
    .weui-media-box__hd{
      img{
        width: 90px;
        border:1px solid transparent;
        border-radius: 10%;
      }
    }
    .weui-media-box__bd{
      .weui-media-box__title{
        position: absolute;
        left:120px;
        top: 10px;
      }
      .weui-media-box__desc{
        position: absolute;
        left: 120px;
        bottom: 12px;
        font-size: 10px;
        .teacher-name-font{
          color:orange;
        }
      }
     .weui-media-box_appmsg .weui-media-box__thumb{
        border-radius: 10%;
      }
    }
  }
}
</style>

