<template>
  <div class="fly-box" ref="flyBox">
    <svg :width="width" :height="height">
        <defs>
            <path
                id="fly-box-path"
                :d="path"
                fill="none"
            />
            <radialGradient
                id="radial-gradient"
                cx="50%"
                cy="50%"
                fx="100%"
                fy="50%"
                r="50%"
            >
                <stop offset="0%" stop-color="#fff" stop-opacity="1"></stop>
                <stop offset="100%" stop-color="#fff" stop-opacity="0"></stop>
            </radialGradient>
            <mask id="fly-box-mask">
                <circle r="150" cx="0" cy="0" fill="url(#radial-gradient)">
                    <animateMotion
                        dur="3s"
                        :path="path"
                        rotate="auto"
                        repeatCount="indefinite"
                    />
                </circle>
            </mask>
        </defs>
        <use
            href="#fly-box-path"
            stroke-width="1"
            stroke="#235fa7"
        />
        <use
            href="#fly-box-path"
            stroke-width="3"
            stroke="#4fd2dd"
            mask="url(#fly-box-mask)"
        />
    </svg>
    <div class="fly-box-content">
        <slot></slot>
    </div>
  </div>
</template>

<script setup>
import { computed, onMounted, ref } from 'vue'

const flyBox = ref()

const width = ref(0)
const height = ref(0)

const path = computed(() => 
    `M5 5 L${width.value - 5} 5 L${width.value - 5} ${height.value - 5} L5 ${height.value - 5} Z`
)

onMounted(() => {
    width.value = flyBox.value.clientWidth
    height.value = flyBox.value.clientHeight
})
</script>

<style lang="scss" scoped>
.fly-box {
    border: 1px solid #000;
    background-color: #333;
    position: relative;
    width: 100%;
    height: 100%;
    svg {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
    }
    &-content {
        width: 100%;
        height: 100%;
        padding: 20px;
    }
}
</style>
