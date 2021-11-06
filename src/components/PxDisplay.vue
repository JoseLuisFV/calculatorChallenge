<template>
  <span class="display">{{ number }}</span>
</template>

<script>
export default {
  name: "PxDisplay",
  props: ["number"],
  data() {
    return {
      valueSaved: 0,
    };
  },
};
</script>

<style lang="scss" scoped>
.display {
  box-sizing: border-box;
  display: block;
  min-width: 320px;
  width: 90%;
  max-width: 640px;
  padding: 20px 25px;
  font-size: 32px;
  text-align: right;
  border-radius: 8px;
}

// colores main

.main .display {
  color: hsl(0, 0, 100%);
  background-color: hsl(224, 36%, 15%);
}

// colores light

.light .display {
  color: hsl(60, 10%, 19%);
  background-color: hsl(0, 0%, 93%);
}

// colores night
.night .display {
  color: hsl(52, 100%, 62%);
  background-color: hsl(268, 71%, 12%);
}
</style>
