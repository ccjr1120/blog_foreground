
<template>
  <div>
    <el-card
      v-for="o in 4"
      :key="o"
      shadow="hover"
      class="box-card"
      :body-style="{ padding: '0px' }"
    >
      <div class="card-content">
        <div style="padding-left:10px;">
          <span style="font-weight:bold;text-align:center">如何去编写一个十分准确的博客标题?</span>
          <br />
          <div style="padding-bottom:5px;padding-left:20px;">
            <span style="font-size:14px">作者没有添加任何描述哦</span>
            <br />
          </div>
        </div>
        <div style="float:left;font-size:14px">发布于2020年01月31日15:58:32</div>
        <div style="float:right;font-size:14px">
          浏览量
          <el-badge :value="2000" class="item" type="info"></el-badge>评论数
          <el-badge :value="122" class="item" type="primary"></el-badge>点赞数
          <el-badge :value="22" class="item" type="success"></el-badge>
        </div>
      </div>
    </el-card>
  </div>
</template>

<style>
.box-card {
  text-align: left;
  margin-bottom: 12px;
  margin-left: 16%;
  width: 60%;
  line-height: 34px;
}
.card-content {
  padding: 20px;
}
</style>