<template>
  <div class="courses-detail">
    <div style="text-align:center;">
      <video height="300" controls="controls" :src='viedeoLink' style="width:100%;">
      </video>
    </div>
    <div class="title-description">
      <p class="headlines">成长规律之英语习惯的培养</p>
      <p class="subtitle">为0-3岁从小习惯的培养</p>
      <span class="icon-title">
        <icon type="success"></icon>
      </span>
    </div>
    <div class="lecturer-techer">
      <router-link to='/teacher-abstract'>
        <img src="@/assets/logo.png">
        <p>
          <span>主讲老师：</span>
          <span class="teacher-name"> 李陶然</span>
        </p>
        <span class="teachers-title">高级教师</span>
        <x-icon type="ios-heart" size="30"></x-icon>
      </router-link>
    </div>
    <div class="teacher-tab">
      <tab>
        <tab-item selected @on-item-click="onItemClick(1)">章节</tab-item>
        <tab-item @on-item-click="onItemClick(2)">详情</tab-item>
        <tab-item @on-item-click="onItemClick(3)">评论</tab-item>
      </tab>
      <chapter-list v-if="current === 1" @coursesVideoClick='onCoursesVideoClick'></chapter-list>
      <comment-list v-else-if="current === 2"></comment-list>
      <detail-list v-else></detail-list>
    </div>

  </div>
</template>

<script>
import { Icon, Tab, TabItem, ViewBox, Panel } from "vux";
import ChapterList from "../courses-detail/chapter-list/index";
import CommentList from "../courses-detail/comment-list/index";
import DetailList from "../courses-detail/detail-list/index";
export default {
  name: "coursesDetail",
  data() {
    return {
      viedeoLink: "",
      current: 1,
      list: [
        {
          title: "xxxx",
          desc:
            '<span>主讲老师：</span><span class="teacher-name-font">李陶然</span>',
          src: require("@/assets/logo.png")
        }
      ]
    };
  },
  components: {
    Icon,
    Tab,
    TabItem,
    ViewBox,
    Panel,
    ChapterList,
    CommentList,
    DetailList
  },
  created() {
    console.log(111, this);
    this.$on("CoursesVideoClick", this.onCoursesVideoClick);
    // document.title = ''
  },
  methods: {
    onItemClick(tab) {
      this.current = tab;
    },
    onCoursesVideoClick(coursesVideoClick) {
      this.viedeoLink = coursesVideoClick;
    },
    onClickTeacher() {
      this.$router.push("/teacher-abstract");
    }
  }
};
</script>

<style lang="less" scoped>
@import "~vux/src/styles/1px.less";
@import "~vux/src/styles/center.less";

.box {
  padding: 15px;
}
.active-6-1 {
  color: rgb(252, 55, 140) !important;
  border-color: rgb(252, 55, 140) !important;
}
.active-6-2 {
  color: orange !important;
  border-color: #04be02 !important;
}
.active-6-3 {
  color: rgb(55, 174, 252) !important;
  border-color: rgb(55, 174, 252) !important;
}
.tab-swiper {
  background-color: #fff;
  height: 100px;
}
</style>
<style lang="less">
.teacher-tab {
  position: relative;
  .vux-tab {
    .vux-tab-ink-bar {
      background: red;
    }
  }
  .vux-tab {
    .vux-tab-item.vux-tab-selected {
      color: red;
    }
  }
}
.title-description {
  position: relative;
  margin-left: 9px;
  margin-bottom: 20px;
  .headlines {
    font-size: 14px;
    font-weight: bold;
  }
  .subtitle {
    color: #ccc;
    font-size: 12px;
    margin-top: 6px;
  }
  .icon-title {
    position: absolute;
    right: 5%;
    top: 0;
  }
}
.lecturer-techer {
  position: relative;
  a:link {
    color: black;
  } /* 未访问的链接 */
  a:visited {
  color: black;
  } /* 已访问的链接 */
  a:hover {
   color: black;
  } /* 当有鼠标悬停在链接上 */
  a:active {
   color: black;
  } /* 被选择的链接 */
  img {
    width: 40px;
    height: 40px;
    border-radius: 50%;
  }
  p {
    position: absolute;
    top: 0;
    left: 60px;
  }
  .teachers-title {
    position: absolute;
    bottom: 0px;
    left: 60px;
    font-size: 12px;
    color: gray;
  }
  .vux-x-icon {
    position: absolute;
    right: 4px;
  }
}
</style>

