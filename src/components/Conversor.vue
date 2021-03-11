<template>
  <div class="conversor">
    <h2>{{ moedaA }} Para {{ moedaB }}</h2>
    <input type="text" v-model="moedaA_value" v-bind:placeholder="moedaA" />
    <input type="button" value="Converter" v-on:click="converter" />
    <h2>{{ moedaB_value }}</h2>
  </div>
</template>

<script>
export default {
  name: "Conversor",
  props: ["moedaA", "moedaB"],
  data() {
    return {
      moedaA_value: "",
      moedaB_value: 0,
    };
  },
  methods: {
    converter() {
      let de_para = `${this.moedaA}-${this.moedaB}`;
      //console.log(de_para)
      let url_conversor = `http://economia.awesomeapi.com.br/json/all/${de_para}`;

      fetch(url_conversor)
        .then((res) => {
          return res.json();
        })
        .then((json) => {
          let cotacao = json[this.moedaA]["high"];
          this.moedaB_value = (parseFloat(this.moedaA_value) * cotacao).toFixed(
            2
          );
          //this.setState({ moedaB_value });
          //console.log(cotacao);
          //console.log(this.moedaB_value);
        });
    },
  },
};
</script>

<style scoped>
.conversor {
  padding: 20px;
  max-width: 300px;
  border-radius: 10px;
  box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.363);
}
.conversor h2 {
  color: #ecd078;
}

div {
  padding: 8px;
}
</style>
