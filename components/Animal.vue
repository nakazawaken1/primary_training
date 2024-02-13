<template>
    <div :style="{'--x': x + 'px', '--y': y + 'px', 'opacity': clicked ? 0.5 : 1}" @click.stop="click"><slot /></div>
</template>

<script lang="ts" setup>
const props = defineProps<{
    width?: number,
    height?: number,
    x: number,
    y: number,
    clicked: boolean,
}>()
const emits = defineEmits<{
    (e: 'click'): void
}>()
</script>

<style lang="scss" scoped>
div {
    position: absolute;
    opacity: var(--opacity);
    left: var(--x);
    top: var(--y);
}
</style>