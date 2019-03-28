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
          
      <div>
        <el-main  >
          <div class="wrapper alerts-container" ref="wrapper" >
    <div class="content" ref="content" :style="{ width: scrollWidth ? scrollWidth + 'px' : '100%' }">
            <Table></Table>
          </div>  
          </div>
        </el-main>
      </div>
    </el-container>
  </el-container>

</template>

<script>
import Sider from "./components/Sider";
import Alert from "./components/Alert";
import Bscroll from "better-scroll";
import Table from "./components/Table";
export default {
  components: {
    Sider,
    Alert,
    Table
  },
  data() {
    return {
      scrollWidth: 0
    };
  },
  methods: {
    resize() {
      if (document.documentElement.clientWidth < 767) {
        this.scrollWidth = 0;
      } else {
        // 计算宽度
        let ls = document.querySelectorAll(".content > .el-table"),
          width = 2000;
        [].forEach.call(ls, el => {
          let rect = el.getBoundingClientRect();
          width += rect.width;
        });
        this.scrollWidth = width;
      }
    }
  },
  mounted() {
    this.$nextTick(() => {
      this.scroll = new Bscroll(this.$refs.wrapper, {
        startX: 0,
        click: true,
        scrollX: true,
        scrollY: true,
        freeScroll: true
      });
    });
    this.resize();

    window.addEventListener("resize", this.resize);
  },
  update() {
    this.resize();
  }
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
}
body {
  overflow-x: hidden;
  overflow-y: hidden;
}
.el-header,
.el-footer {
  color: #333;
  text-align: center;
  line-height: 60px;
}

.el-aside {
  color: #333;
  text-align: center;
  line-height: 200px;
}
.wrapper {
  user-select: none;
  width: 1920px;
  overflow: hidden;
  height: 1080px;
}
.content {
  height: 1520px;
}
</style>
