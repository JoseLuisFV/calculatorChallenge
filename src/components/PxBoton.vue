<template>
  <button :class="['boton', b.type, b.color]">{{ b.value }}</button>
</template>

<script>
export default {
  name: "PxBoton",
  props: ["b"],
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
</style>
