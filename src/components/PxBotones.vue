<template>
  <div class="botones">
    <div class="grilla">
      <px-boton v-for="(boton, i) in botones" :key="i" v-bind:b="boton" />
    </div>
  </div>
</template>

<script>
import PxBoton from "./PxBoton";
export default {
  components: { PxBoton },
  name: "PxBotones",
  componenets: {
    PxBoton,
  },
  data() {
    return {
      botones: [
        { value: 7, type: "number", color: "general" },
        { value: 8, type: "number", color: "general" },
        { value: 9, type: "number", color: "general" },
        { value: "DEL", type: "text", color: "especial" },
        { value: 4, type: "number", color: "general" },
        { value: 5, type: "number", color: "general" },
        { value: 6, type: "number", color: "general" },
        { value: "+", type: "operation", color: "general" },
        { value: 1, type: "number", color: "general" },
        { value: 2, type: "number", color: "general" },
        { value: 3, type: "number", color: "general" },
        { value: "-", type: "operation", color: "general" },
        { value: ".", type: "sintaxis", color: "general" },
        { value: 0, type: "number", color: "general" },
        { value: "/", type: "operation", color: "general" },
        { value: "x", type: "operation", color: "general" },
        { value: "RESET", type: "text", color: "especial" },
        { value: "=", type: "operation", color: "unico" },
      ],
    };
  },
};
</script>

<style lang="scss">
.botones {
  width: 100%;
}

.grilla {
  box-sizing: border-box;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr;
  grid-auto-rows: 65px;
  gap: 15px;
  width: 100%;
  padding: 25px 25px;
  background-color: hsl(223, 31%, 20%);
  border-radius: 12px;
  font-family: "Sparta", sans-serif;
}
</style>
