<template>
    <div>
        <h3 v-for="i in users" :key=i>
            {{i}}
        </h3>
        <button v-on:click="onsub()"> Event BTN</button>

    </div>
</template>


<script>
import func from '../../vue-temp/vue-editor-bridge';
export default {
    name: 'Demo',
    props: ['users'],
    methods:{
        onsub(){
            this.$emit("custEvent",["ABC","PQR","XYZ"])
        }
    },
    created:function(){
        console.log("Created")
    },
    beforeCreate:function(){
        console.log("Before Create")
    },
    beforeMount:function(){
        console.log("Before Mount")
    }
}
</script>