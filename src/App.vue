<template>
  <div id="app">
    <h1>Conversor de Moedas</h1>
    <div class="linha">
      <Conversor moeda-a="USD" moeda-b="BRL" />
      <Conversor moeda-a="BRL" moeda-b="USD" />
    </div>
    <div class="linha">
      <Conversor moeda-a="EUR" moeda-b="USD" />
      <Conversor moeda-a="USD" moeda-b="EUR" />
    </div>
    <div class="linha">
      <Conversor moeda-a="EUR" moeda-b="BRL" />
      <Conversor moeda-a="BRL" moeda-b="EUR" />
    </div>
  </div>
</template>

<script>
import Conversor from "./components/Conversor.vue";

export default {
  name: "App",
  components: {
    Conversor,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
  margin: auto;
  max-width: 900px;
}

body {
  background-color: #53777a;
  /*background: linear-gradient(to right, rgb(83, 105, 118), rgb(41, 46, 73));*/
  font: normal 15pt Arial;
}

h1 {
  text-align: center;
  color: #ecd078;
}

.linha {
  display: flex;
  margin-top: 40px;
  justify-content: space-around;
}
</style>
