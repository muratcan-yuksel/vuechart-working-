<template>
  <BarChart v-bind:someData="someData" v-bind:currencyArray="currencyArray" />
</template>

<script>
import BarChart from "./components/BarChart.vue";
let url =
  "	https://sheltered-scrubland-49038.herokuapp.com/https://api.coindesk.com/v1/bpi/currentprice.json";
export default {
  components: {
    BarChart,
  },
  data() {
    return {
      someData: "",
      currencyArray: [],
    };
  },
  async beforeCreate() {
    try {
      let res = await fetch(url);
      console.log(res);
      let data = await res.json();
      // console.log(data.bpi);
      // wholeData = data.bpi;
      console.log(data.bpi);
      // this.someData = data.bpi;
      for (let currency in data.bpi) {
        // console.log(data.bpi[currency].code);
        this.currencyArray.push(data.bpi[currency].code);
      }
      // barChart.data.labels = names.value;
    } catch (err) {
      console.log(err);
    }
  },
};
</script>

<style></style>
