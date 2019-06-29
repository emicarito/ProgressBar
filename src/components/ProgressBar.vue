<template>
  <b-container>
    <h3 class="text-center mt-3">Barra de progreso 🚥</h3>
    <h3 class="text-center mt-2">{{ contador }}%</h3>
    <div class="text-center mt-3">
      <button class="btn btn-primary mr-1 mb-3" @click="plusContador">+</button>
      <button class="btn btn-danger mb-3" @click="lessContador">-</button>
      <b-progress class="mt-2" :max="max" show-value>
        <b-progress
          :value="value"
          :max="max"
          show-value
          class="mb-3"
          :style="{'width' : contador+'%'}"
          :class="addBackground"
        >{{ contador }}%</b-progress>
      </b-progress>
    </div>
  </b-container>
</template>

<script>
export default {
  name: "ProgressBar",
  data() {
    return {
      contador: 0
    };
  },
  methods: {
    lessContador() {
      if (this.contador > 0) {
        return this.contador--;
      }
      return this.contador;
    },
    plusContador() {
      if (this.contador < 100) {
        return this.contador++;
      }
      return this.contador;
    }
  },
  computed: {
    addBackground() {
      return {
        "bg-success": this.contador < 25,
        "bg-info": this.contador >= 25 && this.contador < 50,
        "bg-warning": this.contador >= 50 && this.contador < 85,
        "bg-danger": this.contador >= 85 && this.contador <= 100
      };
    }
  }
};
</script>

<style scoped>
</style>