<template>
  <group class="courses-list">
    <panel :list="list" @on-click-item="onClickItem"></panel>
  </group>
</template>

<script>
import { Group, Panel } from "vux";
export default {
  name: "coursesList",
  created() {
    console.log(this.$route.query);
    const { title, label } = this.$route.query;
    document.title = `${title}  ${label}`;
  },
  methods: {
    onClickItem() {
      this.$router.push("/courses-detail");
    }
  },
  data() {
    return {
      list: [
        {
          title: "xxxx",
          desc:'<span>主讲老师：</span><span class="teacher-name-font">李陶然</span>',
          src: require("@/assets/logo.png")
        }
      ]
    };
  },
  components: {
    Group,
    Panel
  }
};
</script>

<style lang="less">
.courses-list {
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
</style>

