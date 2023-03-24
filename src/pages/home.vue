<template>
    <div>
        <h2 class="title"><span>{{ text }}</span></h2>
    </div>
</template>
<script lang="ts">
export default {
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
.title {
    color: #333;
    line-height: 2;
}

.title span {
    background: linear-gradient(to right, #fff, #000) no-repeat left bottom;
    background-size: 0 2px;
    transition: background-size 1300ms;
}

.title span:hover {
    background-position-x: left;
    background-size: 100% 2px;
}
</style>