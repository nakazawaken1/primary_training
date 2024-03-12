<template>
  <div class="Fukidashi">
    <div class="shadow"></div>
    <div class="edge-shadow"></div>
    <div class="edge"></div>
    <section>
      <slot></slot>
    </section>
  </div>
</template>

<style lang="scss" scoped>
.Fukidashi {
  position: relative;
  line-height: 84px;
  height: 84px;
  width: 880px;
  font-weight: 800;
  font-size: 35px;
  color: #4EBAC1;

  >.shadow {
    background: #84B0B2;
    opacity: 0.5;
    position: absolute;
    height: 84px;
    width: 880px;
    top: 5px;
    left: 5px;
    border-radius: 30px;
  }

  >section {
    display: flex;
    align-items: center;
    justify-content: center;
    background: #FFFFFF;
    border-radius: 30px;
  }

  >.edge-shadow {
    background: #84B0B2;
    opacity: 0.5;
    position: absolute;
    height: 84px;
    width: 880px;
    width: 48px;
    height: 48px;
    left: calc(50% - 24px);
    bottom: -24px;
    transform: rotate(45deg) translate(5px, 0);
  }

  >.edge {
    position: absolute;
    width: 48px;
    height: 48px;
    left: calc(50% - 24px);
    bottom: -24px;

    background: #FFFFFF;
    transform: rotate(45deg);
  }
}
</style>
