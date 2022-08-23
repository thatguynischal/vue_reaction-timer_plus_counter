<template>
<div class="box"> 
  <h1>Counter App</h1>
<button @click="addNum">+</button> 
<button @click="subNum">-</button>
<h2 v-if="added">Your total is: {{count}}</h2>
  </div>
</template>

<script>
export default {
    data(){
        return{
            count: 0,
            added: false
        }
        
    },
    methods: {
        addNum(){
            this.count = this.count +1
            console.log(this.count)
            this.added=true
        },
        subNum(){
            this.count = this.count -1
            this.added=true
        }
    }

}
</script>

<style>


</style>