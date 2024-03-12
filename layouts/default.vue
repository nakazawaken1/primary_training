<template>
  <main>
    <div>
      <slot />
    </div>
  </main>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=M+PLUS+1:wght@100..900&display=swap');

body {
  margin: 0;
}

* {
  box-sizing: border-box;
  font-family: "M PLUS 1", sans-serif;
}

section,
div {
  position: relative;
}
</style>

<style lang="scss">
main {
  width: 100vw;
  height: 100vh;
  display: grid;
  place-items: center;
  place-content: center;
  background-color: #A5D6D3;

  >div {
    width: 1100px;
    height: 680px;
    border-radius: 30px;
    background-color: #FFFFFF;
    display: grid;
    place-items: center;
  }
}
</style>
