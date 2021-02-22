<template>
  <div class="keypad">
    <div class="row">
      <div class="col-md-4 p-0" v-for="i in btnArray" :key="i">
        <button class="btn btn-secondary w-100" v-on:click="myClick(i)">
          {{ i }}
        </button>
      </div>
      <div
        v-bind:class="{ 'col-md-4': i == '+', 'col-md-2': i != '+' }"
        class="p-0"
        v-for="i in btncal"
        :key="i"
      >
        <button class="btn btn-secondary w-100" v-on:click="myClick(i)">
          {{ i }}
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "KeyPad",
  data() {
    return {
      btnArray: ["1", "2", "3", "4", "5", "6", "7", "8", "9", ".", "0","CE"],
      btncal: ["+", "-", "x", "/", "="],
      calstr: "",
    };
  },
  methods: {
    myClick(par) {
      
      this.$emit('clicked', par,this.btncal)
    },
  },
};
</script>
<style scoped>
.keypad button {
  height: 70px;
  font-size: 25px;
  border-radius: 0;
}
</style>
