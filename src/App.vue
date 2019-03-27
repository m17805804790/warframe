<template>
  <el-container>
    <el-header>
      <el-menu mode="horizontal">
        <el-menu-item index="1">处理中心</el-menu-item>
        <el-submenu index="2">
          <template slot="title">我的工作台</template>
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
        <el-menu-item index="3">消息中心</el-menu-item>
        <el-menu-item index="4">订单管理</el-menu-item>
    </el-menu>
    </el-header>
    <el-container >
      <el-aside style="height:100vh;width:65px"><Sider/></el-aside>
          
      <el-main>Main</el-main>
    </el-container>
  </el-container>

</template>

<script>
import Sider from './components/Sider'
export default {
  components:{
    Sider,
  },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<style>
  *{
    margin:0;
    padding:0;
  }
  .el-header, .el-footer {
   
    color: #333;
    text-align: center;
    line-height: 60px;
  }
  
  .el-aside {
    
    color: #333;
    text-align: center;
    line-height: 200px;
  }
  
  .el-main {
    background-color: #E9EEF3;
    color: #333;
    text-align: center;
    line-height: 160px;
  }
  
  
  

</style>
