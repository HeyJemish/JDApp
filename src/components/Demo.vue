<template>
    <div>
        <h3 v-for="i in users" :key=i>
            {{i}}
        </h3>
        <button v-on:click="onsub()"> Event BTN</button>

    </div>
</template>


<script>
export default {
    name: 'Demo',
    props: ['users'],
    methods:{
        onsub(){
            this.$emit("custEvent",["ABC","PQR","XYZ"])
        }
    },
    beforeCreate:function(){
        console.log("Before Create")
    },
    created:function(){
        console.log("Created")
    },
    beforeMount:function(){
        console.log("Before Mount")
    },
    mounted:function(){
        console.log("Mounted")
    }
}
</script>