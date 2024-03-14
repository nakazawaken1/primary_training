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
  user-select: none;
}

section,
div {
  position: relative;
}

@keyframes step1 {
  0% {
    opacity: 0;
    display: none;
  }
  50% {
    opacity: 0;
    display: none;
  }
  51% {
    opacity: 1;
    display: block;
  }
  100% {
    opacity: 1;
    display: block;
  }
}
@keyframes step2 {
  0% {
    opacity: 0;
    display: none;
  }
  49% {
    opacity: 0;
    display: none;
  }
  50% {
    opacity: 1;
    display: block;
  }
  100% {
    opacity: 1;
    display: block;
  }
}
.frame1 {
  animation: step1 2s infinite;
}
.frame2 {
  animation: step2 2s infinite reverse;
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
