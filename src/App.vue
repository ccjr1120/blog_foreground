<template>
  <div id="app" class="fillcontain">
    <el-container class="fillcontain">
      <el-header>
        <el-menu default-active="home" class="el-menu-demo" mode="horizontal" router>
          <el-menu-item index="/">
            <div style="width:140px;">Mysterious Blog</div>
          </el-menu-item>
          <el-menu-item index="home">Home</el-menu-item>
          <el-menu-item index="about">About me</el-menu-item>
          <el-menu-item index="reading">Reading</el-menu-item>
        </el-menu>
      </el-header>
      <el-container>
        <el-aside>
          <el-row class="tac">
            <el-col>
              <el-menu :default-openeds="['1']" router class="el-menu-vertical-demo">
                <el-submenu index="1">
                  <template slot="title">
                    <i class="el-icon-menu"></i>
                    <span>分组列表</span>
                  </template>
                  <el-menu-item-group>
                    <el-menu-item index="1-1">选项1</el-menu-item>
                    <el-menu-item index="1-2">选项2</el-menu-item>
                  </el-menu-item-group>
                </el-submenu>
              </el-menu>
            </el-col>
          </el-row>
        </el-aside>
        <el-main><router-view/></el-main>
      </el-container>
    </el-container>
  </div>
</template>

<style scope>
html,
body,
#app,
.el-container {
  padding: 0px;
  margin: 0px;
  height: 100%;
}
.el-header {
  color: #333;
  text-align: center;
  line-height: 60px;
  /* margin-left: 180px; */
}

.el-aside {
  width: 200px !important;
  color: #333;
  text-align: center;
  line-height: 200px;
}

.el-main {
  background-color: #e9eef3;
  color: #333;
  text-align: center;
  line-height: 160px;
}

body > .el-container {
  margin-bottom: 40px;
}

.el-container:nth-child(5) .el-aside,
.el-container:nth-child(6) .el-aside {
  line-height: 260px;
}

.el-container:nth-child(7) .el-aside {
  line-height: 320px;
}
</style>
