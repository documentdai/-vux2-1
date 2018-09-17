<template>
    <div class="course-share">
        <div class="course-share-main">
            <div class="share-nav">
                <img src='../../../images/01.jpg'>
                <h3>创业的365堂必修课</h3>
                <p>跟着品牌教练学创业，365天每天一节创业课</p>
            </div>
            <div class="share-main">
                <group>
                    <panel :list='list'>
                    </panel>
                </group>
            </div>
            <hr>
            <div class="share-footer">
                <img src="../../../images/01.jpg" class="share-qr-code">
                <img src="../../../images/01.jpg" class="share-icon">
                <span>
                    <p>长按识别二维码</p>
                    <p>查看课程</p>
                </span>
            </div>
        </div>
    </div>
</template>

<script>
const list = [
  {
    src: "http://somedomain.somdomain/x.jpg",
    fallbackSrc: "http://placeholder.qiniudn.com/60x60/3cc51f/ffffff",
    title: "<span>我是：</span><span>微信昵称</span>",
    desc: "加入实现4.3亿家庭教育普及行列",
    url: "/component/cell"
  }
];
import { Panel, Group } from "vux";
export default {
  name: "course-share",
  data() {
    return {
      list
    };
  },
  components: {
    Panel,
    Group
  }
};
</script>

<style lang="less">
.course-share {
  background: url("../../../images/01.jpg") 100% 100%;
  height: 100%;
  .course-share-main {
    background: #ffffff;
    border: 1px solid transparent;
    border-radius: 5%;
    overflow: hidden;
    margin: 40px;
    .share-nav {
      margin: 20px;
      img {
        padding-top: 10px;
        width: 100%;
        height: 150px;
        border: 1px solid transparent;
        border-radius: 15%;
      }
      p {
        margin-top: 15px;
        color: gray;
        font-size: 15px;
      }
    }
    .share-main {
      position: relative;
      margin-top: 10px;
      .weui-media-box__hd {
        img {
          width: 60px;
          height: 60px;
          border: 1px solid transparent;
          border-radius: 50%;
        }
      }
      .weui-media-box__bd {
        .weui-media-box__title {
          position: absolute;
          left: 80px;
          top: 15px;
        }
        .weui-media-box__desc {
          position: absolute;
          left: 80px;
          bottom: 15px;
          font-size: 14px;
          color: orange;
          .teacher-name-font {
            color: orange;
          }
        }
        .weui-media-box_appmsg .weui-media-box__thumb {
          border-radius: 10%;
        }
      }
    }
    .share-footer {
          width: 100%;
          margin: 10% 0 10% 10%;
          position: relative;
        .share-qr-code {
          width: 100px;
          height: 100px;
        }
        .share-icon{
            width: 50px;
            position: absolute;
            right: 25%;
            bottom: 40%;
        }
        span{
            position: absolute;
            right: 20%;
            bottom: 2%;
            text-align: center;
            font-size: 12px;
            color: orange;
        }
      }
  }
}
</style>

