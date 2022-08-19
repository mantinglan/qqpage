<template>
  <div>
    <el-radio-group v-model="isCollapse" style="margin-bottom: 20px; width:100px">
      <el-radio-button :label="false">展开</el-radio-button>
      <el-radio-button :label="true">收起</el-radio-button>
    </el-radio-group>
    <el-menu default-active="2" class="el-menu-vertical-demo" @open="handleOpen" @close="handleClose" :collapse="isCollapse">
    
      <el-menu-item index="1" @click="changeRoute()">
        <i class="el-icon-s-home"></i>
        <span slot="title">關於 / About</span>
      </el-menu-item>
      <el-menu-item index="2">
        <i class="el-icon-menu"></i>
        <span slot="title">房型介紹 / Rooms</span>
      </el-menu-item>
      <el-menu-item index="3">
        <i class="el-icon-document"></i>
        <span slot="title">訂房須知 / Notice</span>
      </el-menu-item>
      <el-menu-item index="4" >
        <i class="el-icon-location-outline"></i>
        <span slot="title">聯絡我們 / Contact Us</span>
      </el-menu-item>
    </el-menu>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        isCollapse: true
      };
    },
    methods: {
      handleOpen(key, keyPath) {
        console.log(key, keyPath);
      },
      handleClose(key, keyPath) {
        console.log(key, keyPath);
      },
      changeRoute(){
        this.$router.push({ name:'about' })
      }
    }
  }
</script>

<style scoped>
.el-menu-vertical-demo:not(.el-menu--collapse) {
    width: 250px;
    min-height: 400px;
  }

</style>
