<template>
    <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" :stroke="strokeColor"
        stroke-width="strokeWidth" stroke-linecap="round" stroke-linejoin="round" >
        <path :fill="pathColor"
            d="m15.477 12.89 1.515 8.526a.5.5 0 0 1-.81.47l-3.58-2.687a1 1 0 0 0-1.197 0l-3.586 2.686a.5.5 0 0 1-.81-.469l1.514-8.526" />
        <circle :cx="12" :cy="8" :r="6" :fill="circleColor" />
    </svg>
</template>

<script setup>

const props = defineProps({
    strokeColor: {
        type: String,
        default: "#000"
    },
    pathColor: {
        type: String,
        default: "#d89912"
    },
    circleColor: {
        type: String,
        default: "#eeab1b"
    },
    strokWidth: {
        type: String,
        default: "0.6"
    }
})
</script>
