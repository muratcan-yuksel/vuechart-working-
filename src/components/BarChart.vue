<script>
import { defineComponent } from "vue";
import { Pie } from "vue3-chart-v2";

export default defineComponent({
  name: "MonthlyChart",
  extends: Pie,
  props: ["someData", "currencyArray", "rateArray"],
  data() {
    return {
      currency: "",
      Data: null,
    };
  },

  mounted() {
    // Overwriting base render method with actual data.
    this.renderChart({
      labels: this.currencyArray,
      datasets: [
        {
          label: "Exchange Rates",
          backgroundColor: ["#f87979", "yellow", "black"],
          data: this.rateArray,
        },
      ],
    });
    // console.log(this.Data);
    // console.log(this.renderChart);
    // console.log(this.someData);
    console.log(this.currencyArray);
    console.log("rates " + this.rateArray);
  },
});
</script>
