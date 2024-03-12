<template>
  <div class="Stage">
    <slot />
    <nav v-if="status">
      <Life :current="status.life" :max="status.lifeMax" />
      <Score :current="status.score" :max="status.scoreMax" />
    </nav>
    <footer>
      <Sound />
      <label>プレイかいすう<strong>15</strong>回　　さいこうきろく：レベル <strong>3 / 02:46</strong>
        　
        <ButtonStop />
      </label>
    </footer>
  </div>
</template>

<script lang="ts" setup>
const props = defineProps<{
  status?: { life: number, lifeMax: number, score: number, scoreMax: number } | null,
  isUpperStatus?: boolean,
}>()
</script>

<style lang="scss" scoped>
.Stage {
  width: 1070px;
  height: 650px;
  border-radius: 15px;
  background-color: #D8F4FA;
  position: relative;

  >nav {
    width: 307px;
    height: 70px;
    background: #fff;
    border-top-left-radius: 20px;
    position: absolute;
    bottom: 55px;
    right: 0;
    display: flex;
    align-items: center;
    justify-content: space-evenly;
  }

  >footer {
    padding: 0 5px;
    position: absolute;
    display: grid;
    align-items: center;
    grid-template-columns: 1fr auto;
    bottom: 0;
    left: 0;
    right: 0;
    text-align: center;
    font-size: 18px;
    font-weight: bold;
    color: #999;
    background-color: #fff;
    line-height: 40px;
    padding-top: 15px;

    >label {
      display: flex;
      align-items: center;

      >strong {
        font-size: 24px;
        padding: 0 5px;
      }
    }
  }
}
</style>