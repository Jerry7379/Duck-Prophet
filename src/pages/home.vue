<template>
    <div>
        <h2>css相关的一些奇技淫巧</h2>
        <h2 class="title"><span>{{ text }}</span></h2>
        <img class="auto-head" src="../assets/head2.png" alt="头像">
        <CssRotatingBall></CssRotatingBall>

        <div class="btn">
            鼠标移入展示窗口
            <div class="detail">
                <div class="content">
                    <div class="inner">
                        Lorem ipsum dolor, sit amet consectetur adipisicing elit. Quibusdam voluptatum eaque ex
                        aperiam
                        saepe! Veniam quaerat adipisci quia. Tempore sit eaque placeat, mollitia nam impedit dolores
                        perferendis
                        quos
                        quisquam velit?
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script lang="ts">
import CssRotatingBall from "../components/CssRotatingBall.vue";

export default {
    data() {
        return {
            text: "搞点不一样的下划线"
        };
    },
    methods: {},
    components: { CssRotatingBall }
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

.auto-head {
    --s: 280px;
    --c1: #c02942;
    --c2: #fff;
    --b: 5px;
    --f: 1;
    --bgOption: content-box no-repeat center/ calc(100% / var(--f)) 100%;
    --shrink: calc((var(--s) / var(--f) - var(--s)) / 2 - var(--b));

    width: var(--s);
    height: var(--s);
    cursor: pointer;
    transition: scale(var(--f));
    padding-top: 50px;
    outline: var(--b) solid var(--c1);
    outline-offset: var(--shrink);
    border-radius: 0 0 999px 999px;
    transform: scale(var(--f));
    background: radial-gradient(circle closest-side,
            var(--c2) calc(99% - var(--b)),
            var(--c1) calc(100% - var(--b)),
            var(--c1) 99%,
            transparent 100%) var(--bgOption);
    -webkit-mask:
        linear-gradient(#000 0 0) no-repeat center calc(1px - var(--shrink)) / calc(100% / var(--f) - 2 * var(--b) - 1px) 50%,
        radial-gradient(circle closest-side, #000 99%, transparent) var(--bgOption);
}

.auto-head:hover {
    --f: 1.35
}

.content {
    background-color: #222;
    color: #fff;
    line-height: 1.5;
    min-height: 0;
}

.inner {
    padding: 20px;
}

.detail {
    display: grid;
    grid-template-rows: 0fr;
    transition: .5s;

}

.btn:hover .detail {
    grid-template-rows: 1fr;
}
</style>