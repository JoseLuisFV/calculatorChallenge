<template>
  <button :class="['boton', b.type, b.color]" v-on:click="sendValue($event)">
    {{ b.value }}
  </button>
</template>

<script>
export default {
  name: "PxBoton",
  props: ["b"],
  methods: {
    sendValue() {
      this.$emit("catch-value", this.b.value);
    },
  },
};
</script>

<style lang="scss" scoped>
@import url("https://fonts.googleapis.com/css2?family=Spartan:wght@700&display=swap");
.number {
  font-size: 32px;
}

.operation {
  font-size: 32px;
}

.sintaxis {
  font-size: 32px;
}

.text {
  font-size: 18px;
}

.boton {
  border: none;
  border-radius: 8px;
  font-family: "Spartan", sans-serif;
}

.boton:nth-last-child(2) {
  grid-column-start: 1;
  grid-column-end: 3;
}

.boton:nth-last-child(1) {
  grid-column-start: 3;
  grid-column-end: 5;
}

// colores main

.main .general {
  background-color: hsl(30, 25%, 89%);
  box-shadow: 0px 5px hsl(28, 16%, 65%);
  color: hsl(221, 14%, 31%);
}

.main .especial {
  background-color: hsl(225, 21%, 49%);
  box-shadow: 0px 5px hsl(224, 28%, 35%);
  color: hsl(0, 0, 100%);
}

.main .unico {
  background-color: hsl(6, 63%, 50%);
  box-shadow: 0px 5px hsl(6, 70%, 34%);
  color: hsl(0, 0, 100%);
}

// colores light

.light .general {
  background-color: hsl(45, 7%, 89%);
  color: hsl(60, 10%, 19%);
  box-shadow: 0px 5px hsl(35, 11%, 61%);
}

.light .especial {
  background-color: hsl(185, 42%, 37%);
  color: hsl(0, 0, 100%);
  box-shadow: 0px 5px hsl(185, 58%, 25%);
}

.light .unico {
  background-color: hsl(25, 98%, 40%);
  color: hsl(0, 0%, 100%);
  box-shadow: 0px 5px hsl(25, 99%, 27%);
}

// colores night
.night .general {
  background-color: hsl(268, 47%, 21%);
  color: hsl(52, 100%, 62%);
  box-shadow: 0px 5px hsl(290, 70%, 36%);
}

.night .especial {
  background-color: hsl(281, 89%, 26%);
  color: hsl(0, 0, 100%);
  box-shadow: 0px 5px hsl(285, 91%, 52%);
}

.night .unico {
  background-color: hsl(176, 100%, 44%);
  color: hsl(198, 20%, 13%);
  box-shadow: 0px 5px hsl(177, 92%, 70%);
}
</style>
