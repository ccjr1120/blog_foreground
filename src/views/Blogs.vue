
<template>
  <div>
    <div class="box-card" v-for="blog in blogList" :key="blog.label">
      <router-link :to="'/showblog/'+blog.bid">
        <el-card @click="showTheBlog" shadow="hover" :body-style="{ padding: '0px' }">
          <div slot="header">
            <span>{{blog.title}}</span>
            <div style="padding-left:10px;">
              <div style="padding-bottom:5px;padding-left:20px;">
                <span style="font-size:14px">博客内容简述...</span>
                <el-button size="small" style="padding: 10px 0px" type="text">查看更多</el-button>
              </div>
            </div>
          </div>
          <div class="card-content">
            <div style="float:left;font-size:14px">发布于{{blog.createDate}}</div>
            <div style="float:right;font-size:14px">
              浏览量
              <el-badge :value="2000" class="item" type="info"></el-badge>评论数
              <el-badge :value="122" class="item" type="primary"></el-badge>点赞数
              <el-badge :value="22" class="item" type="success"></el-badge>
            </div>
          </div>
        </el-card>
      </router-link>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      blogList: []
    };
  },
  watch: {
    //watch router changes
    $route(to, from) {
      window.console.log(from);
      this.getBlogsByCategroy(this.$route.params.name);
    }
  },
  methods: {
    getBlogsByCategroy(categoryName) {
      this.$axios.get("common/blogList/" + categoryName).then(resp => {
        var data = resp.data;
        if (data.success) {
          this.blogList = data.data;
        }
      });
    },
    showTheBlog: bid => {
      alert(bid);
    }
  }
};
</script>
<style>
.box-card {
  text-align: left;
  margin-bottom: 12px;
  margin-left: 16%;
  width: 60%;
  line-height: 34px;
}
.card-content {
  padding: 3px;
}
.el-card__header {
  padding-bottom: 4px !important;
}
a {
  text-decoration: none;
}
</style>