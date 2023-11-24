<template>
  <div class="container">
    <svg width="440" height="440" viewBox="0 0 440 440">
        <circle cx="220" cy="220" r="200" stroke-width="20" stroke="#d1d3d7" fill="transparent"></circle>
        <!-- 圆形的周长 - 2*3.1415926*r = 1257 -->
        <circle cx="220" cy="220" r="200" stroke-width="20" stroke="#00a5e0" fill="transparent" class="circle" transform="matrix(0 -1 1 0 0 440)"></circle>
    </svg>
  </div>  
</template>

<script setup>
import {} from 'vue'
</script>

<style lang="scss" scoped>
.container {
    border: 1px solid #000;
}
.circle {
    animation: circle 5s linear infinite;
}

@keyframes circle {
    from {
        stroke-dasharray: 0 1257;
    }
    to {
        stroke-dasharray: 1257 0;
    }
}
</style>
