<template>
  <el-container class="layout">
    <el-header class="navWrapper">
      <div id="menu" :class="{ active: isActive, inactive: !isActive }">
        <el-menu mode="horizontal" @select="handleSelect" :router="true">
          <el-menu-item index="1" :route="{ name: 'index' }">
            <i class="el-icon-s-home"></i>
            <span slot="title">關於</span>
          </el-menu-item>
          <el-menu-item index="2" :route="{ name: 'about' }">
            <i class="el-icon-menu"></i>
            <span slot="title">房型介紹</span>
          </el-menu-item>
          <el-menu-item index="3">
            <i class="el-icon-document"></i>
            <span slot="title">訂房須知</span>
          </el-menu-item>
          <el-menu-item index="4" >
            <i class="el-icon-phone-outline"></i>
            <span slot="title">聯絡我們</span>
          </el-menu-item>
        </el-menu>
      </div>
      <div id="toggle" @click="select()">
        <div class="span" id="top" :class="{ active: isActive }"></div>
        <div class="span" id="middle" :class="{ active: isActive }"></div>
        <div class="span" id="bottom" :class="{ active: isActive }"></div>
      </div>
    </el-header>
    <el-main class="mainContainer" :class="{ active: isActive }">
      <Nuxt />
    </el-main>
    <el-footer class="footer">
      <div class="footer-div">
        <span class="footer-span">&copy; Darcy</span>
      </div>
    </el-footer>
  </el-container>
</template>
<script>
  export default {
    data() {
      return {
        isCollapse: true,
        isActive: false,
      };
    },
    methods: {
      handleOpen(key, keyPath) {
        console.log(key, keyPath);
      },
      handleClose(key, keyPath) {
        console.log(key, keyPath);
      },
      changeRoute(route){
        this.$router.push({ name: route })
      },

    handleSelect(key, keyPath) {
      console.log(key, keyPath);
      this.isActive = false;
    },
    select: function() {
      this.isActive = !this.isActive;
    }
    }
  }
</script>

<style scoped lang="scss">
.el-menu-vertical-demo:not(.el-menu--collapse) {
    /* width: 250px; */
    height: 100%;
  }
  .layout {
    display: flex;
    flex-direction: column;
    height: 100vh;
  }

  .logo-header {
    padding-left: 15px;
    padding-right: 50px;
    z-index: 100;
  }

  .navWrapper {
    width: 100%;
    // position: fixed;
    top: 0;
  }

  #logo.el-menu-item.is-active {
    border-bottom-color: transparent;
  }

  #toggle {
    position: absolute;
    right: 20px;
    top: 14px;
    z-index: 999;
    width: 30px;
    height: 30px;
    cursor: pointer;
    float: right;
    transition: all .3s ease-out;
    visibility: hidden;
    opacity: 0;
  }

  #toggle .span {
    border-radius: 10px;
    background: black;
    transition: all 0.5s ease-out;
    backface-visibility: hidden;
  }

  #top.span.active {
    transform: rotate(45deg) translateX(3px) translateY(5px);
  }

  #middle.span.active {
    opacity: 0;
  }

  #bottom.span.active {
    transform: rotate(-45deg) translateX(8px) translateY(-10px);
  }

  .el-menu {
    display: flex;
    justify-content: space-between;
  }
  @media only screen and (max-width: 768px) {

    .logo-header {
      padding: 0;
    }
  .mainContainer {
    position: relative;
    height: 100%;
  }
    #toggle {
      visibility: visible;
      opacity: 1;
      margin-top: 6px;
    }

    #toggle .span {
      height: 4px;
      margin: 5px 0;
      transition: all .3s ease-out;
      backface-visibility: visible;
      visibility: visible;
      opacity: 1;
    }

    #menu .el-menu-item {
      display: none;
      // visibility: hidden;
    }
    .el-menu {
    display: block;
  }

    #menu.active {
      margin: 70px 0;
      visibility: visible;
      opacity: 0.98;
      transition: all .5s ease-out;
      .el-menu--horizontal .el-menu-item {
        text-align: center;
        float: none;
        display: block;
        height: 100%;
        width: 100%;
        border-top: 1px solid #EAEAEB;
        font-size: 18px;
        visibility: visible;
      }
    }
    #menu.inactive {
      transition: all .5s ease-out;
    }
    .mainContainer.active {
      // position: relative;
      visibility: hidden;
    }
  }

.el-footer {
  display: flex;
  height: 4vh;
  width: 100%;
  align-items: center;
}
  .footer {
    // background-image: linear-gradient(90deg,#6bd4ee,#1aa5ca);
    // border-radius: 0 72px 0 0;
    // background: #555559 none repeat scroll 0 0;
    color: #999999;
    background-color: #a6a6a63b;
  }
</style>
