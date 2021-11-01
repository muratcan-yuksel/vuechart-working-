<script>
import { defineComponent } from "vue";
import { Bar } from "vue3-chart-v2";

export default defineComponent({
  name: "MonthlyChart",
  extends: Bar,
  props: ["someData", "currencyArray"],
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
          label: "GitHub Commits",
          backgroundColor: "#f87979",
          data: [40, 20, 12, 39, 10, 40, 39, 80, 40, 20, 12, 11],
        },
      ],
    });
    // console.log(this.Data);
    // console.log(this.renderChart);
    // console.log(this.someData);
    console.log(this.currencyArray);
  },
});
</script>
