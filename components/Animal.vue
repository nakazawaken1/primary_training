<template>
  <div :style="{ '--x': x + 'px', '--y': y + 'px', 'opacity': clicked ? 0.5 : 1 }">
    <component :is="names.get(name)" @hit="emits('hit')" />
  </div>
</template>

<script lang="ts" setup>
const names = new Map([
  ["buta", resolveComponent('AnimalButa')],
  ["kaba", resolveComponent('AnimalKaba')],
  ["kame", resolveComponent('AnimalKame')],
  ["lion", resolveComponent('AnimalLion')],
  ["saru", resolveComponent('AnimalSaru')],
  ["shimauma", resolveComponent('AnimalShimauma')],
  ["tora", resolveComponent('AnimalTora')],
  ["usagi", resolveComponent('AnimalUsagi')],
  ["zou", resolveComponent('AnimalZou')],
])
const props = defineProps<{
  x?: number,
  y?: number,
  clicked?: boolean,
  name: string,
}>()
const emits = defineEmits<{
  (e: 'hit'): void
}>()
</script>

<style lang="scss" scoped>
div {
  position: absolute;
  opacity: var(--opacity);
  left: var(--x);
  top: var(--y);
  cursor: pointer;
}
</style>