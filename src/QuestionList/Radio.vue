<script setup lang="ts">
    import {computed} from 'vue'

    const props = defineProps({
        activated: Boolean,
        defaultColor: String,
        activatedColor: String,
        size: Number
    })
    
    const emit = defineEmits(['click'])

    const classprops = computed<string>(()=>props.activated?'activated':'')
    const size = computed(()=>{
        if(props.size) return `calc(${(props.size)}*var(--size))`
        else return 'var(--size)'
    })

    const click = ()=>emit('click')
</script>

<template>
    <span :class="classprops" @click="click"></span>
</template>

<style scoped>
    @media screen and (max-width: 480px) {
        * {
            --size: 42px;
        }
    }
    @media screen and (min-width: 480px) {
        * {
            --size: 80px;
        }
    }
    span::before {
        content: '●';
        cursor: pointer;
        vertical-align: middle;
        font-family: Arial, Helvetica, sans-serif;
        color: #FFFFFF;
        font-size: v-bind(size);
        -webkit-text-stroke: 3px v-bind(props.defaultColor);
    }
    span.activated::before, span:hover::before {
        animation-duration: 0.4s;
        animation-name: check;
        color: v-bind(props.defaultColor);
    }
    @keyframes check {
        from {
            color: #FFFFFF;
        }
        to {
            color: v-bind(props.defaultColor);
        }
    }
</style>