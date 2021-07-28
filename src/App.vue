<template>
<div>
  <h1>My to do list</h1>
  <form action="">
    <input type="text" placeholder="example buy candy..." v-model="addToList">
    <button @click.prevent="valid">Add</button>
  </form>
  <ul v-for="(item,index) in myTabs"
  v-bind:key="index">
    <li v-bind:style="{background: color, padding: margeInt, display: visibility}" @click='supp'>{{item}}</li>
  </ul>
</div>
</template>

<script>

export default {
  name: 'App',
 data:function(){
   return{
     addToList: '',
     myTabs: [],
     color: 'pink',
     margeInt: '10px',
     visibility : true
   }
 },methods:{
   valid:function(){
     this.myTabs.push(this.addToList)
    this.addToList = ''
   },

 }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
input, button{
  padding: 10px;
}
</style>
