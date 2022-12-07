<script setup lang="ts">
</script>

<template>
    <div @click="" class="nextbtn">
        <span>查看报告</span>
        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 5l7 7-7 7M5 5l7 7-7 7"></path></svg>
    </div>
</template>

<style scoped>
    .nextbtn {
        display: flex;
        flex-direction: row;
        padding: 20px 40px;
        margin: 15px;
        align-items: center;
        justify-content: center;
        border-radius: 50px;
        color: white;
        background-image: linear-gradient(to right top, #88619a, #7c548f, #704883, #653b78, #592f6d);
        cursor: pointer;
    }
    .nextbtn>span {
        padding: 0px 20px;
    }
    .nextbtn>svg {
        height: 1.2em;
    }
    .nextbtn:hover>svg {
        animation-name: arrow;
        animation-duration: 1s;
        animation-iteration-count: infinite;
    }
    @keyframes arrow{
        0% {
            margin-left: 0;
        }
        40% {
            margin-left: 10px;
        }
        100% {
            margin-left: 0;
        }
    }
</style>