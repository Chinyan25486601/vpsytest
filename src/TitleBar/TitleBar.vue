<template>
    <div class="titlebar">
        <svg class="logo" viewBox="0 0 128 128" width="24" height="24" data-v-e0ef77de=""><path fill="#42b883" d="M78.8,10L64,35.4L49.2,10H0l64,110l64-110C128,10,78.8,10,78.8,10z" data-v-e0ef77de=""></path><path fill="#35495e" d="M78.8,10L64,35.4L49.2,10H25.6L64,76l38.4-66H78.8z" data-v-e0ef77de=""></path></svg>
        <div>VPsyTest</div>
        <div>-</div>
        <div id="d">Psychology Test Framework <br/>Powered by Vue</div>
    </div>
</template>

<style scoped>
    .titlebar {
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: center;
        z-index: 100;
        background-color: #FFFFFF;
        width: 100%;
        height: fit-content;
        padding-top: 15px;
        padding-bottom: 15px;
        border-bottom: 1px solid rgba(60, 60, 60, .29);
    }
    .titlebar>* {
        padding-top: 10px;
        padding-bottom: 10px;
        margin: 0 5px;
    }
    #d {
        align-self: flex-end;
        color: gray;
    }
</style>