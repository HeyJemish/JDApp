<template>
  <div class="container calcont bg-secondary py-5">
    <div class="row">
      <div class="col-md-12">
        <div class="h2 float-right text-white">
          {{ calstring }}
        </div>
      </div>
      <div class="col-md-12">
        <div class="h2 float-right text-white">{{ anstring }}</div>
      </div>
      <div class="col-md-12">
        <CalcKeypad @clicked="setstring" />
      </div>
    </div>
  </div>
</template>

<script>
// import CalcAns from "../components/CalcAns.vue";
import CalcKeypad from "../components/CalcKeypad.vue";

export default {
  name: "Calc",
  components: {
    // CalcAns,
    CalcKeypad,
  },
  data() {
    return {
      calstring: "0",
      anstring: "",
      ch: "",
    };
  },
  methods: {
    setstring(value) {
      if (this.calstring == 0) {
        this.calstring = "";
      }
      if (value != "=" && value != "CE") {
        this.calstring = this.calstring + value;

        if (this.calstring == "+") {
          this.calstring = this.anstring + value;
        }
        if (this.calstring == "-") {
          this.calstring = this.anstring + value;
        }
        if (this.calstring == "x") {
          this.calstring = this.anstring + value;
        }
        if (this.calstring == "/") {
          this.calstring = this.anstring + value;
        }
      }

      if (value == "CE") {
        this.calstring = "0";
        this.anstring = "";
      }
      if (value == "+") {
        this.ch = 1;
      } else if (value == "-") {
        this.ch = 2;
      } else if (value == "x") {
        this.ch = 3;
      } else if (value == "/") {
        this.ch = 4;
      } else if (value == "=") {
        var arr = [];
        if (this.ch == 1) {
          arr = this.calstring.split("+");
          this.anstring = (parseFloat(arr[0]) + parseFloat(arr[1])).toString();
          this.calstring = "";
          // this.calstring = this.anstring;
        } else if (this.ch == 2) {
          arr = this.calstring.split("-");
          this.anstring = parseFloat(arr[0]) - parseFloat(arr[1]).toString();
          this.calstring = "";
          // this.calstring = this.anstring;
        } else if (this.ch == 3) {
          arr = this.calstring.split("x");
          this.anstring = parseFloat(arr[0]) * parseFloat(arr[1]).toString();
          this.calstring = "";
          // this.calstring = this.anstring;
        } else if (this.ch == 4) {
          arr = this.calstring.split("/");
          this.anstring = parseFloat(arr[0]) / parseFloat(arr[1]).toString();
          this.calstring = "";
          // this.calstring = this.anstring;
        }
      }
    },
  },
};
</script>

<style scoped>
.calcont {
  border: 15px solid gainsboro;
  border-radius: 15px;
  width: 400px;
}
</style>
