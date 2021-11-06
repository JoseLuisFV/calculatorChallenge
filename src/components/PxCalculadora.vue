<template>
  <div :class="['wrapper', theme]">
    <px-header v-model="theme" v-on:send-theme="applyTheme" />
    <px-display v-bind:number="number" />
    <px-botones
      v-on:send-number="addNumber"
      v-on:send-operation="makeOperation"
    />
  </div>
</template>

<script>
import PxBotones from "./PxBotones";
import PxHeader from "./PxHeader";
import PxDisplay from "./PxDisplay";
export default {
  name: "Calculadora",
  components: {
    PxHeader,
    PxBotones,
    PxDisplay,
  },
  data() {
    return {
      theme: "main",
      number: "0",
      savedNumber: "",
      operacion: "",
    };
  },
  methods: {
    applyTheme(t) {
      console.log(t);
      if (t === "main") {
        this.theme = "main";
      } else if (t === "light") {
        this.theme = "light";
      } else {
        this.theme = "night";
      }
    },
    addNumber(n) {
      console.log(n);
      if (this.number === "0") {
        this.number = n.toString();
      } else {
        if (n != ".") {
          this.number += n.toString();
        }
        if (n == "." && !this.number.includes(".")) {
          this.number += n.toString();
        }
      }
    },
    makeOperation(o) {
      if (o === "RESET") {
        this.savedNumber = "";
        this.number = "0";
      } else if (o === "DEL") {
        const longitud = this.number.length;
        if (longitud != 1) {
          this.number = this.number.substring(0, longitud - 1);
        } else {
          this.number = "0";
        }
      } else {
        this.operacionAritmetica(o);
      }
    },
    operacionAritmetica(o) {
      if (!this.operacion.length && o != "=") {
        this.operacion = o;
        this.savedNumber = this.number;
        this.number = "0";
      } else {
        if (this.operacion == "+") {
          const bruto = parseFloat(this.savedNumber) + parseFloat(this.number);
          this.number = bruto.toFixed(2).toString();
        } else if (this.operacion == "-") {
          const bruto = parseFloat(this.savedNumber) - parseFloat(this.number);
          this.number = bruto.toFixed(2).toString();
        } else if (this.operacion == "x") {
          const bruto = parseFloat(this.savedNumber) * parseFloat(this.number);
          this.number = bruto.toFixed(2).toString();
        } else if (this.operacion == "/") {
          const bruto = parseFloat(this.savedNumber) / parseFloat(this.number);
          this.number = bruto.toFixed(2).toString();
        }
        this.operacion = "";
      }
    },
  },
};
</script>

<style lang="scss" scoped>
.wrapper {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 30px;
  width: 100%;
}

.main {
  background-color: hsl(222, 26%, 31%);
}

.light {
  background-color: hsl(0, 0%, 90%);
}

.night {
  background-color: hsl(268, 75%, 9%);
}
</style>
