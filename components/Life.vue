<template>
    <svg v-for="(x, i) of lifes" :key="i" width="34" height="34" viewBox="0 0 34 34" fill="none" xmlns="http://www.w3.org/2000/svg">
        <circle v-if="x" cx="17" cy="17" r="17" fill="#E72838" />
        <path
            d="M24.65 6.25L28.4 9.9L20.95 17.35L28.3 24.75L24.65 28.45L17.2 21.1L9.85 28.4L6.2 24.7L13.45 17.35L6.15 10L9.85 6.25L17.2 13.55L24.65 6.25Z"
            :fill="x ? '#FFFFFF' : '#CCCCCC'" />
    </svg>
</template>

<script lang="ts" setup>
const props = withDefaults(defineProps<{
    current: number,
    max: number,
}>(), {
    current: 3,
    max: 3,
})
const lifes = computed(() => new Array(props.max).fill(true).concat(new Array(props.current).fill(false)).slice(-props.max))
</script>
