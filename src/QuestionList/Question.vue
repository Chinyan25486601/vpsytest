<script setup lang="ts">
    import { reactive,computed } from 'vue';
    
    import Radio from './Radio.vue';

    const props = defineProps({
        activated: Boolean,
        question: String
    })

    const green = 'rgb(51,164,116)'
    const gray = 'rgb(155,159,170)'
    const red = 'rgb(136,97,154)'   // actually purple

    const radiosDefinition = <{id:number, defaultColor:string, activatedColor:string, size:number}[]>[
        {id:0, defaultColor: green, size:1.5},
        {id:1, defaultColor: green, size:1.2},
        {id:2, defaultColor: gray, size:1},
        {id:3, defaultColor: red, size:1.2},
        {id:4, defaultColor: red, size:1.5},
    ]
    const radiosStatus = reactive<boolean[]>([false,false,false,false,false])
    const click = (n:number)=>{
        if(radiosStatus[n]!=true){
            for(let i in radiosStatus){
                radiosStatus[i]=false
            }
            radiosStatus[n]=true
        }
    }

    const classprops = computed(()=>props.activated?"":"inactive")
</script>

<template>
    <div :class="'question '+classprops">
        <div class="title">{{props.question}}</div>
        <div class="options">
            <span class="agree description">同意</span>
            <Radio v-for="radio in radiosDefinition"
                v-bind="radio"
                @click="()=>{click(radio.id)}"
                :activated="radiosStatus[radio.id]"></Radio>
            <span class="against description">反对</span>
        </div>
    </div>
</template>

<style scoped>
    .question {
        min-width: 70%;
        overflow: hidden;
        border-bottom: 1px solid v-bind(gray);
        display: flex;
        justify-items: center;
        align-items: center;
        flex-direction: column;
    }
    .inactive {
        filter: opacity(.3) grayscale(.5);
    }
    .title {
        font-size: 1.2em;
        font-weight: bold;
        margin-top: 1.2em;
    }
    .options {
        width: 100%;
        /* display: flex; */
        place-items: center;
        height: 120px;
        padding-bottom: 1.2em;
    }
    .description {
        display: inline-block;
        vertical-align: middle;
    }
    .agree {
        color: v-bind(green)
    }
    .against {
        color: v-bind(red)
    }
    @media screen and (max-width: 900px) {
        .options>* {
            margin-left: 1px;
            margin-right: 1px;
        }
        .options {
            padding-bottom: 0px;
        }
        .description {
            writing-mode: vertical-lr;
            font-size: 0.8em;
        }
    }
    @media screen and (min-width: 900px) {
        .options>* {
            margin-left: 12px;
            margin-right: 12px;
        }
        .question {
            width: 60%;
            overflow: visible;
        }
    }
</style>