<template>
  <el-row>
    <el-col :span="7">
      <img :src="imgurl">
    </el-col>
    <el-col :span="12">
      <el-menu :router="true" :default-active="$route.path" class="el-menu" mode="horizontal" @select="handleSelect"
               background-color="#545c64"
               text-color="#fff"
               active-text-color="#ffd04b">
        <el-menu-item index="/map">站点地图</el-menu-item>
        <el-submenu index="2">
          <template slot="title">站点监控</template>
          <el-menu-item index="2-1">选项1</el-menu-item>
          <el-menu-item index="2-2">选项2</el-menu-item>
          <el-menu-item index="2-3">选项3</el-menu-item>
          <el-submenu index="2-4">
            <template slot="title">选项4</template>
            <el-menu-item index="2-4-1">选项1</el-menu-item>
            <el-menu-item index="2-4-2">选项2</el-menu-item>
            <el-menu-item index="2-4-3">选项3</el-menu-item>
          </el-submenu>
        </el-submenu>
        <el-submenu index="3">
          <template slot="title">站点控制</template>
          <el-menu-item index="/remote_control">远程控制</el-menu-item>
          <el-menu-item index="/time_control">定时控制</el-menu-item>
        </el-submenu>
        <el-menu-item index="4">运营维护</el-menu-item>
        <el-menu-item index="/test">系统管理</el-menu-item>
      </el-menu>
    </el-col>
  </el-row>
</template>

<script>
  export default {
    name: 'vHeader',
    data () {
      return {
        imgurl: require('@/assets/logo.png')
      }
    },
    methods: {
      handleSelect (key, keyPath) {
        console.log(key, keyPath)
      }
    }
  }
</script>

<style scoped>
  .el-menu {
    z-index: 1000;
  }
</style>
