<template>
  <div class="h1 float-right ">
    {{ calculation == null ? "0" : calculation }}
  </div>
</template>

<script>
export default {
  name: "Answer Window",
  props: ["calculation"],
};
</script>

<style scoped>
.AnsCmp {
  background: gainsboro;
}
</style>
