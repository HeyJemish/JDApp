<template>
    <div class="AnsCmp">
        <h1>{{calculation}}</h1>
    </div>
</template>

<script>
export default {
    name: "Answer Window",
    props: ['calculation']
}
</script>

<style scoped>
.AnsCmp {
    background: gainsboro;
}
</style>