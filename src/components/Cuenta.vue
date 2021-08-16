<template>
  <h2>Tipo de cuenta: {{ tipo }}</h2>
  <h2>Saldo: {{ saldo }}</h2>
  <h2>Cuenta {{ estado ? "Activa" : "Inactiva" }}</h2>
  <div v-for="(item, index) in servicios" :key="index">
    {{ index + 1 }} - {{ item }}
  </div>
  <AccionSaldo
    texto="Aumentar Saldo"
    clase="btn-primary"    
    @accionSaldo="aumentarSaldo"
  />

  <AccionSaldo
    texto="Disminuir Saldo"
    clase="btn-danger"
    :desactivar="saldo"
    @accionSaldo="disminuirSaldo"
  />

    <AccionSaldo
    texto="Resetear Saldo"
    clase="btn-warning"
    @accionSaldo="resetSaldo"
  />
</template>

<script>
import AccionSaldo from "./AccionSaldo.vue";

export default {
  components: {
    AccionSaldo,
  },
  data() {
    return {
      saldo: 1000,
      tipo: "Corriente",
      estado: true,
      servicios: ["Créditos", "Abonos", "Transferencias"],
    };
  },
  methods: {
    aumentarSaldo() {
      this.saldo += 100;
    },
    disminuirSaldo() {
      if(this.saldo === 0){
        alert('Saldo insuficiente');
        return;
      }

      this.saldo -= 100;
    },
    resetSaldo(){
      this.saldo = 0;
    }
  },
};
</script>

<style></style>
