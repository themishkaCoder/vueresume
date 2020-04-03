<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<style lang="scss">
@import url('https://fonts.googleapis.com/css?family=Montserrat&display=swap&subset=cyrillic');

*{
  padding: 0;
  margin: 0;
}
body{
  overflow: hidden;
}
#app {
  // font-family: Avenir, Helvetica, Arial, sans-serif;
  font-family: 'Montserrat', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  // color: #2c3e50;
}

</style>
