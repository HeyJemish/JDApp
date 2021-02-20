<template>
    <div>
        <p v-text="name"></p>
        {{name}}
    </div>
</template>

<script>
export default {
    name: 'component_name',
    props : ['name'],
    data(){
        return {
            email :'',
            myArr : ['val1','val2','val3']
        }
    },    
}
</script>


<style scoped>
div {
    color: red;
    padding: 25px;
    background: gainsboro;
}
</style>