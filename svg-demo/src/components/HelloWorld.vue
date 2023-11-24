<template>
  <!-- 环形进度条 -->
  <SvgCircle />
  <!-- 小球跟随 -->
  <Ball />
  <!-- 描边动画 -->
  <Logo />
  <!-- svg 动画 -->
  <svgSM />
  <!-- svg loading -->
  <svgLoading :width="200" :height="100">
      <span>数据加载中</span>
  </svgLoading>
  <!-- svg 飞线 -->
  <FlyBox style="width: 400px;height: 400px;">
      <div>111</div>
      <div>222</div>
      <div>333</div>
  </FlyBox>
</template>

<script setup>
import SvgCircle from './SVG/SvgCircle.vue'
import Ball from './SVG/Ball.vue'
import Logo from './SVG/Logo.vue'
import svgSM from './SVG/svgSM.vue'
import svgLoading from './SVG/svgLoading.vue'
import FlyBox from './SVG/FlyBox.vue'
</script>

<style lang="scss" scoped></style>