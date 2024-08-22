<template>
  <div class="ld-div">
    <div v-if="isMobile" class="mobile-tip">
      请在pc上打开
    </div>
    <LuckDraw v-else />
  </div>
</template>

<script>
import LuckDraw from './components/LuckDraw.vue';
import judgeDevice from '@/tools/judgeDevice';

export default {
  name: 'App',
  components: {
    LuckDraw
  },
  data() {
    return {
      isMobile: false,
    }
  },
  mounted() {
    this.isMobile = judgeDevice();
  },
}
</script>

<style lang="scss">
.ld-div {
  // height: 100vh;
  // width: 100vw;
  .mobile-tip {
    color: salmon;
    text-align: center;
    font-size: 22px;
    margin-top: 50px;
  }
}
</style>
