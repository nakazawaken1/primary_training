<template>
    <nav>
        <strong>{{ current }}</strong>
        <span>/{{ max }}</span>
    </nav>
</template>

<script lang="ts" setup>
const props = withDefaults(defineProps<{
    current: number,
    max: number,
}>(), {
    current: 5,
    max: 5,
})
</script>

<style lang="scss" scoped>
nav {
    color: #4EBAC1;
    font-weight: bold;
    padding: 0 10px;

    strong {
        font-size: 100px;
    }

    span {
        font-size: 70px;
    }
}
</style>