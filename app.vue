<template>
  <main>
    <div>
      <ClickTraining />
    </div>
  </main>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans:wght@400;700&display=swap');

body {
  margin: 0;
  font-family: 'Noto Sans', sans-serif;
}
</style>

<style lang="scss">
main {
  width: 100vw;
  height: 100vh;
  display: grid;
  place-items: center;
  place-content: center;
  background-color: #222222;

  >div {
    position: relative;
    width: 1100px;
    height: 700px;
    border-radius: 30px;
    background-color: #FFFFFF;
  }
}
</style>
