<template>
  <header class="header">
    <h1 class="titulo">calc</h1>
    <span class="theme">{{ theme }}</span>
    <form class="controlls">
      <label class="controlls__title" for="main">1</label>
      <label class="controlls__title" for="light">2</label>
      <label class="controlls__title" for="night">3</label>
      <div class="options">
        <input
          class="option"
          type="radio"
          value="main"
          id="main"
          v-model="theme"
          v-on:change="changeTheme($event)"
        />
        <input
          class="option"
          type="radio"
          value="light"
          id="light"
          v-model="theme"
          v-on:change="changeTheme($event)"
        />
        <input
          class="option"
          type="radio"
          value="night"
          id="night"
          v-model="theme"
          v-on:change="changeTheme($event)"
        />
      </div>
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
    changeTheme(event) {
      const data = event.target.value;
      this.$emit("send-theme", data);
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
  min-width: 320px;
  width: 90%;
  max-width: 640px;
}

.titulo {
  margin-top: 0;
  margin-bottom: 0;
}

.theme {
  margin-right: 0;
  margin-left: auto;
  letter-spacing: 2px;
  text-transform: uppercase;
}

.controlls {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-template-areas:
    "main light night"
    "options options options";
  margin-right: 0;
  margin-left: 20px;
  gap: 8px;
  text-align: center;

  .options {
    box-sizing: border-box;
    display: flex;
    justify-content: space-between;
    align-content: center;
    gap: 10px;
    padding: 3px;
    grid-area: options;
    border-radius: 16px;

    input[type="radio"] {
      box-sizing: border-box;
      appearance: none;
      background-color: none;
      font: inherit;
      width: 20px;
      height: 20px;
      border-radius: 50%;
    }

    .option {
      margin: 0;
    }
  }
}

// Colores main

.main .header {
  color: hsl(0, 0, 100%);
}

.main .options {
  background-color: hsl(223, 31%, 20%);
}

.main input[type="radio"] {
  border: 0.15em solid hsl(224, 36%, 15%);
}

.main input[type="radio"]:checked {
  background-color: hsl(6, 70%, 34%);
}

// colores light

.light .header {
  color: hsl(60, 10%, 19%);
}

.light .options {
  background-color: hsl(0, 5%, 81%);
}

.light input[type="radio"] {
  border: 0.15em solid hsl(0, 0%, 93%);
}

.light input[type="radio"]:checked {
  background-color: hsl(25, 98%, 40%);
}

// colores night
.night .header {
  color: hsl(52, 100%, 62%);
}

.night .options {
  background-color: hsl(268, 71%, 12%);
}

.night input[type="radio"] {
  border: 0.15em solid hsl(281, 89%, 26%);
}

.night input[type="radio"]:checked {
  background-color: hsl(176, 100%, 44%);
}
</style>
