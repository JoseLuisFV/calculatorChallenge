<template>
  <div :class="['wrapper', theme]">
    <px-header />
    <px-display />
    <px-botones />
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
    };
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
  min-width: 320px;
  width: 90%;
  max-width: 680px;
}
</style>
