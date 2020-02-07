<template>
  <div>
    <VueMarkDown :source="blogContent"></VueMarkdown>
  </div>
</template>

<script>
import VueMarkDown from "vue-markdown";
export default {
  data() {
    return {
      blogContent: ""
    };
  },
  created() {
    var blogId = this.$route.params.bid;
    this.$axios.get("/common/blog/" + blogId).then(resp => {
      if (resp.data.success) {
        this.blogContent = resp.data.data;
      }
    });
  },
  components:{
    VueMarkDown
  }
};
</script>

<style scope>
.el-main{
  line-height: 140%;
  text-align: left
}
</style>