<template>
    <div class="box"></div>
</template>
<script lang="ts">
export default {
    name: "cssRotaingBall",
    data() {
        return {
            text: "搞点不一样的下划线"
        }
    },
    methods: {

    }
}
</script>
<style scoped>
.box {
    width: 200px;
    height: 200px;
    background: transparent;
    /* 背景透明 */
    border: 5px solid #00d9ff;
    border-radius: 50%;
    position: relative;
    animation: round 2s infinite;
}

.box:before {
    position: absolute;
    top: 15px;
    left: 10px;
    content: "";
    width: 30px;
    height: 30px;
    background: rgb(255, 132, 0);
    border-radius: 50%
}

@keyframes round {
    0% {
        rotate: 0deg;
    }

    100% {
        rotate: 360deg;
    }
}
</style>