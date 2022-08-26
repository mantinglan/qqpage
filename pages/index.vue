<template>
  <div class="container">
    <header class="header">
      <div class="text-box">
        <h1 class="heading-primary">
          <span class="heading-primary-main">Q&Q</span>
          <span class="heading-primary-sub">宜蘭包棟民宿</span>
        </h1>
      </div>
    </header>
    <div class="body">
      <div></div>
    </div>
  </div>
</template>


<script>
import Menu from '../components/Menu.vue';
export default {
    name: "IndexPage",
    layout: 'front',
    components: { Menu }
}
</script>

<style lang="scss">
  .container {
    display: flex;
    flex-direction: column;
  }
  .header {
    height: 80vh;
    max-width: 100%;
    background-size: cover;
    background-position: center;
    background-image: url('@/assets/image/olaf.jpeg');
    .text-box {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
    }
    .heading-primary {
      color: #fff;
      .heading-primary-main{
        display: block;
        font-size: 60px;
        font-weight: 700;
        letter-spacing: 35px;
      }
      .heading-primary-sub{
        display: block;
        font-size: 22px;
        font-weight: 500;
        letter-spacing: 15px;
      }
    }
  }
  .body {
    height: 1000px;
    overflow: auto;
    background-color: aqua;
  }
</style>