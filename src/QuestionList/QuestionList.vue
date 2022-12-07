<script setup lang="ts">
    import Question from "./Question.vue"
    import NextButton from "./NextButton.vue"
    import FinishButton from "./FinishButton.vue"
</script>

<template>
    <Question v-for="i in new Array(2)" question="你发现你正在访问VPsyTest的测试页面。" :activated="false"></Question>
    <Question question="你发现你正在访问VPsyTest的测试页面。" :activated="true"></Question>
    <Question v-for="i in new Array(1)" question="你发现你正在访问VPsyTest的测试页面。" :activated="false"></Question>
    <NextButton></NextButton>
    <!-- <FinishButton></FinishButton> -->
</template>

<style scoped>
</style>