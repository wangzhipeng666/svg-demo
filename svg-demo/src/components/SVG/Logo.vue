<template>
  <div class="logo-wrap">
    <svg viewBox="0 0 1024 1024" width="200" height="200">
        <path class="logo" d="M648.456898 941.757335H374.304446c-5.026282 0-9.131249 4.115204-9.13125 9.141486v36.545471c0 20.217733 16.337975 36.555708 36.555708 36.555708h219.32401c20.217733 0 36.555708-16.337975 36.555707-36.555708v-36.545471c-0.010237-5.026282-4.115204-9.141486-9.151723-9.141486zM511.38579 0.491368C304.519999 0.491368 136.707701 168.293429 136.707701 375.169457c0 138.67829 75.394228 259.769711 187.333926 324.538114v132.392878c0 20.217733 16.337975 36.555708 36.555708 36.555708h301.576911c20.217733 0 36.555708-16.337975 36.555708-36.555708V699.707571c111.939699-64.768402 187.333926-185.849587 187.333926-324.538114C886.06388 168.303666 718.261819 0.491368 511.38579 0.491368zM657.485779 628.541152l-41.008727 23.759675v134.102428H406.294529v-134.102428L365.285801 628.541152c-89.899811-51.972369-146.325199-147.707171-146.325199-253.371695 0-161.51665 130.908538-292.425188 292.425188-292.425188 161.526887 0 292.435425 130.908538 292.435425 292.425188 0 105.664524-56.435625 201.399326-146.335436 253.371695z m0 0"></path>
    </svg>
  </div>
</template>

<script setup>
import { onMounted } from 'vue';

onMounted(() => {
    // 获取logo描边长度
    const path = document.getElementsByClassName('logo')[0]
    const pathLen = path.getTotalLength()
    console.log(pathLen) // 5458.33056640625
})
</script>

<style lang="scss" scoped>
.logo-wrap {
    border: 1px solid #000;
}
.logo {
    fill: none;
    stroke: #333;
    stroke-width: 2;
    animation: logo 5s linear infinite forwards;
}
@keyframes logo {
    0% {
        fill: white;
        stroke-dasharray: 5459;
        stroke-dashoffset: 5459;
    }
    50% {
        fill: white;
        stroke-dasharray: 5459;
        stroke-dashoffset: 0;
    }
    75% {
        fill: red;
        stroke: white;
    }
    100% {
        fill: blue;
        stroke: white;
    }
}
</style>
