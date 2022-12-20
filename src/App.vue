<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
</script>

<template>
  <p>
    Diameter tangki air {{ Diameter }} Cm
  </p> <br>
  <p>
    Tinggi tangki air {{ Tinggi }} Cm / {{ TinggiM }} Meter
  </p> <br>
  <p>
    Jari-jari tangki air {{ Jari }} Cm / {{ JariM }} Meter
  </p> <br>
  <p>
    Volume tangki air {{ Result }} Liter
  </p> <br>
</template>

<script>
  export default {
    name: "App",

    data() {
      return {
        Diameter: 80,
        Tinggi: 100,
        Jari: 0,
        JariM: 0,
        TinggiM: 0,
        Volume: 0,
        Result: 0
      };
    },

    mounted() {
      this.Jari = this.Diameter / 2;
      this.JariM = this.Jari / 100;
      this.TinggiM = this.Tinggi / 100;
      this.Volume = (this.JariM * this.JariM * this.TinggiM * (22/7)) * 1000;
      this.Result = this.Volume.toFixed(2);
    }
  };
</script>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
