<template>
  <div class="svg-loading">
    <svg :width="width" :height="height" viewBox="0 0 50 50" preserveAspectRatio="xMidYMid meet">
        <circle
            cx="25"
            cy="25"
            r="22"
            fill="none"
            stroke-width="3"
            stroke="#3be6cb"
            stroke-dasharray="34"
            stroke-linecap="round"
        >
            <animateTransform
                attributeName="transform"
                type="rotate"
                values="0 25 25;360 25 25"
                dur="1.5s"
                repeatCount="indefinite"
            />
            <animate
                attributeName="stroke"
                values="#3be6cb;#02bcfe;#3be6cb"
                dur="4s"
                repeatCount="indefinite"
            />
        </circle>
        <circle
            cx="25"
            cy="25"
            r="12"
            fill="none"
            stroke-width="3"
            stroke="#02bcfe"
            stroke-dasharray="19"
            stroke-linecap="round"
        >
            <animateTransform
                attributeName="transform"
                type="rotate"
                values="360 25 25;0 25 25"
                dur="1.5s"
                repeatCount="indefinite"
            />
            <animate
                attributeName="stroke"
                values="#02bcfe;#3be6cb;#02bcfe"
                dur="4s"
                repeatCount="indefinite"
            />
        </circle>
    </svg>
    <div class="loading-tip">
      <slot />
    </div>
  </div>
</template>

<script setup>
const props = defineProps(['width', 'height'])
</script>

<style lang="scss" scoped>
.svg-loading {
    border: 1px solid #000;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}
.loading-tip {
    font-size: 15px;
}
</style>
