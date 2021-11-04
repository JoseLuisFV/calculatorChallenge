<template>
  <header class="header">
    <h1 class="titulo">calc</h1>
    <span class="theme">{{ theme }}</span>
    <form class="controlls">
      <label for="main">
        1<br />
        <input type="radio" value="main" id="main" v-model="theme" />
      </label>
      <label for="light">
        2<br />
        <input type="radio" value="light" id="light" v-model="theme" />
      </label>
      <label for="night">
        3<br />
        <input type="radio" value="night" id="night" v-model="theme" />
      </label>
    </form>
  </header>
</template>

<script>
export default {
  data() {
    return {
      theme: "main",
    };
  },
  methods: {
    changeColor() {
      this.color = "main";
    },
  },
};
</script>

<style lang="scss">
.header {
  display: flex;
  position: relative;
  align-items: center;
  height: 80px;
  width: 100%;
  color: hsl(0, 0, 100%);
}

.titulo {
  flex-basis: auto;
  margin-top: 0;
  margin-bottom: 0;
}

.theme {
  flex-basis: auto;
  margin-right: 0;
  margin-left: auto;
}

.controlls {
  flex-basis: auto;
  margin-right: 0;
  margin-left: 20px;
}
</style>
