<template>
  <div class="botones">
    <div class="grilla">
      <px-boton
        v-for="(boton, i) in botones"
        :key="i"
        v-bind:b="boton"
        v-on:catch-value="filterValue"
      />
    </div>
  </div>
</template>

<script>
import PxBoton from "./PxBoton";
export default {
  components: { PxBoton },
  name: "PxBotones",
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
  methods: {
    filterValue(v) {
      if (typeof v == "number" || v === ".") {
        this.$emit("send-number", v);
      } else if (typeof v == "string") {
        this.$emit("send-operation", v);
      }
    },
  },
};
</script>

<style lang="scss">
.botones {
  min-width: 320px;
  width: 90%;
  max-width: 640px;
}

.grilla {
  box-sizing: border-box;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr;
  grid-auto-rows: 65px;
  gap: 25px 20px;
  width: 100%;
  padding: 25px 25px;
  border-radius: 12px;
  font-family: "Sparta", sans-serif;
}

// colores main

.main .grilla {
  background-color: hsl(223, 31%, 20%);
}

// colores light

.light .grilla {
  background-color: hsl(0, 5%, 81%);
}

// colores night

.night .grilla {
  background-color: hsl(268, 71%, 12%);
}
</style>
