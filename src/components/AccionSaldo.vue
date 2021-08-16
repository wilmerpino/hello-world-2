<template>
  <button
    class="btn m-1"
    :class="clase"
    @click="accion"
    :disabled="desactivar === 0"
  >
    {{ texto }}
  </button>
</template>

<script>
export default {
  props: {
    texto: String,
    clase: String,
    desactivar: {
      type: Number,
      default: 1,
    },
  },
  methods: {
    accion() {
      this.$emit("accionSaldo");
    },
  },
};
</script>

<style></style>