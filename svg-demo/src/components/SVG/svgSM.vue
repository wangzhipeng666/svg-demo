<template>
  <div class="svg-smil">
    <!-- 移动的小球 -->
    <svg width="200" height="200">
        <circle cx="0" cy="0" r="30" fill="blue" stroke="black" stroke-width="1">
            <animate attributeName="cx" attributeType="XML" from="0" to="100" dur="3s" repeatCount="2" fill="freeze"></animate>
            <animate attributeName="cy" attributeType="XML" from="0" to="50" dur="3s" repeatCount="2" fill="freeze"></animate>
            <animate attributeName="fill" attributeType="XML" from="blue" to="red" dur="3s" repeatCount="2" fill="freeze"></animate>
            <animateTransform attributeName="transform" attributeType="XML" begin="0" dur="3s" type="scale" from="1" to="0.5" repeatCount="2" fill="freeze"></animateTransform>
        </circle>
    </svg>
    <!-- 形状补间动画 -->
    <svg width="200" height="200">
        <polygon points="30 30 70 30 90 70 10 70" fill="#fcc" stroke="black">
            <animate attributeName="points" attributeType="XML" to="50 30 70 50 50 90 30 50" dur="5s" fill="freeze" repeatCount="1"></animate>
        </polygon>
    </svg>
    <!-- click点击触发动画 -->
    <svg width="200" height="200">
        <g id="rect1">
            <rect x="0" y="0" fill="red" width="100" height="100">
                <animate attributeName="fill" attributeType="XML" from="red" to="green" dur="2s" fill="freeze" begin="rect1.click"></animate>
            </rect>
        </g>
        <animateTransform attributeName="transform" attributeType="XML" dur="2s" type="translate" from="0, 0" to="50, 50" begin="rect1.click" fill="freeze"></animateTransform>
        <rect x="0" y="100" fill="blue" width="100" height="100">
            <animate attributeName="fill" attributeType="XML" from="blue" to="green" dur="2s" fill="freeze" begin="rect1.click"></animate>
        </rect>
    </svg>

    <!-- animateMotion标签 -->
    <!-- 按照path轨迹运动的正方形 -->
    <div class="motion">
        <svg width="200" height="200">
            <rect x="0" y="0" fill="red" width="10" height="10">
                <animateMotion path="M10 10 L110 10 L110 110 L10 110 Z" dur="5s" rotate="0" fill="freeze" repeatCount="2"></animateMotion>
            </rect>
            <path d="M10 10 L110 10 L110 110 L10 110 Z" fill="none" stroke="green"></path>
        </svg>
        <svg width="200" height="200">
            <rect x="0" y="0" fill="red" width="10" height="10">
                <animateMotion
                    id="forward-rect"
                    begin="0; backward-rect.end+0.5s"
                    path="M10 10 L110 10 L110 110 L10 110"
                    dur="3s"
                    rotate="0"
                    fill="freeze"
                ></animateMotion>
                <animateMotion
                    id="backward-rect"
                    begin="forward-rect.end+0.5s"
                    path="M10 110 L110 110 L110 10 L10 10"
                    dur="3s"
                    rotate="0"
                    fill="freeze"
                ></animateMotion>
                <animate id="red-to-blue" attributeName="fill" attributeType="XML" from="red" to="blue" dur="3s" repeatCount="2" fill="freeze" begin="0; blue-to-red+0.5s"></animate>
                <animate id="blue-to-red" attributeName="fill" attributeType="XML" from="blue" to="red" dur="3s" repeatCount="2" fill="freeze" begin="red-to-blue+0.5s"></animate>
            </rect>
            <path d="M10 10 L110 10 L110 110 L10 110" fill="none" stroke="green"></path>
        </svg>
    </div>
  </div>
</template>

<script setup>

</script>

<style lang="scss" scoped>
.svg-smil {
    border: 1px solid #000;
}
.motion {
    margin-top: 20px;
}
</style>
