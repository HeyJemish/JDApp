<template>
  <div class="about">
    <h1>This is an about page</h1>
    <div v-bind:class={success:type,error:!type}>
      Hello
    </div>
    <div v-bind:class=[arr]>
      World
    </div>
    <div><button v-bind:class="[!type?'success':'error']">Submit</button></div>
    <demo v-bind:users="users" v-on:custEvent="getData($event)" />
  </div>
</template>




<script>

import demo from '@/components/Demo.vue'

export default {
  components: {
    demo
  },
  data(){
    return{
      type:0,
      arr:'className',
      users:["Jemish","Steve","Tony","Bucky","Natasha"]
    }
  },
  methods : {
    getData(data){
        this.users = data;
    }
  }
}
</script>

<style scoped>
.success{
  color: blue;
}
.error{
  color: red;
}
.className{
  color:rgb(119, 123, 161);
}
</style>