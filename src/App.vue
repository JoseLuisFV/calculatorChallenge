<template>
  <div id="app">
    <px-calculadora />
  </div>
</template>

<script>
import PxCalculadora from "./components/PxCalculadora.vue";
export default {
  name: "App",
  components: {
    PxCalculadora,
  },
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Spartan:wght@700&display=swap");
body {
  min-height: 100vh;
  margin: 0;
  padding: 0;
  font-family: "Spartan", sans-serif;
}

#app {
  display: flex;
  justify-content: center;
  align-content: center;
  box-sizing: border-box;
  background-color: hsl(222, 26%, 31%);
  min-height: 100vh;
}
</style>
