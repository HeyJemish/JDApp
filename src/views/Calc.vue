<template>
    <div class="main">
        <h2>My First App</h2>
        <CalcAns />
        <CalcKeypad />
    </div>
    
</template>

<script>
import CalcAns from '../components/CalcAns.vue'
import CalcKeypad from '../components/CalcKeypad.vue'

export default {
    name : "Calc",
    components: {
        CalcAns,
        CalcKeypad 
    }
}
</script>


<style scoped>
    .main{
        width: 50%;
        margin-left: auto;
        margin-right: auto;
        background: gainsboro;
    }
</style>