<template>
  <button type="button"
    :style="{ '--width': width + 'px', '--height': height + 'px', '--background': hover ? 'linear-gradient(0deg, #FF6C98 0%, #F6336D 100%)' : 'linear-gradient(180deg, #4EBAC1 0%, #059EA8 100%)' }">
    <slot />
  </button>
</template>

<script lang="ts" setup>
const props = withDefaults(defineProps<{
  hover: boolean,
  width?: number,
  height?: number,
}>(), {
  hover: false,
  width: 400,
  height: 80,
})
</script>

<style lang="scss" scoped>
button {
  appearance: none;
  cursor: pointer;
  width: var(--width);
  height: var(--height);
  background: var(--background);
  border: 5px solid #FFFFFF;
  box-shadow: 0px 5px 5px rgba(156, 151, 145, 0.15);
  border-radius: 10px;
  font-family: 'M PLUS 1';
  font-style: normal;
  font-weight: 800;
  font-size: 30px;
  line-height: 22px;
  display: flex;
  align-items: center;
  justify-content: center;
  letter-spacing: 2px;
  color: #FFFFFF;
}
</style>
