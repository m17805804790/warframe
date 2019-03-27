<template>
    <el-menu mode="vertical">
        <el-tooltip class="item" effect="dark" content="Right Center 提示文字" placement="right">
            <el-menu-item index="1">      
                <i class="el-icon-menu"></i>
            </el-menu-item>
        </el-tooltip>
        <el-tooltip class="item" effect="dark" content="Right Center 提示文字" placement="right">
            <el-menu-item index="2">      
                <i class="el-icon-menu"></i>
            </el-menu-item>
        </el-tooltip>
        <el-tooltip class="item" effect="dark" content="Right Center 提示文字" placement="right">
            <el-menu-item index="3">      
                <i class="el-icon-menu"></i>
            </el-menu-item>
        </el-tooltip>
        <el-tooltip class="item" effect="dark" content="Right Center 提示文字" placement="right">
            <el-menu-item index="4">      
                <i class="el-icon-menu"></i>
            </el-menu-item>
        </el-tooltip>
    </el-menu>
</template>

<script>
export default {
    name:"Sider",
  data () {
    return {
      msg: '123'
    }
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>

