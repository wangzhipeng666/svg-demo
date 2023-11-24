<template>
    <div id="foo" class="ball"></div>
</template>

<script setup>
import { onMounted } from 'vue';

onMounted(() => {
    const f = document.getElementById('foo')
    document.addEventListener('click', (ev) => {
        f.style.transform = `translateY(${ev.clientY-25-25}px)`
        f.style.transform += `translateX(${ev.clientX-25-850}px)`
    }, false)
    // 监听动画开始和结束事件
    f.addEventListener('transitionstart', () => {
        console.log('start')
    }, true)
    f.addEventListener('transitionend', () => {
        console.log('end')
    }, true)
})
</script>

<style lang="scss" scoped>
.ball {
    width: 50px;
    height: 50px;
    border-radius: 25px;
    background-color: #c00;
    position: absolute;
    top: 25px;
    left: 850px;
    transition: transform 1s;
}
.demo {
    width: 200px;
    height: 200px;
    border: 2px solid red;
    padding: 20px;
    margin-top: 20px;
}
.demo1 {
    width: 200px;
    height: 200px;
    border: 2px solid red;
    padding: 20px;
    margin-top: 20px;
    box-sizing: border-box;
}
</style>
