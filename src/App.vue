<template>
<div>
  <h1>My to do list</h1>
  <form action="" @submit.prevent="valid">
    <input type="text" placeholder="example buy candy..." v-model="addToList">
    <button >Add</button>
  </form>
  <ul v-for="(item,index) in myTabs"
  v-bind:key="index">
    <li :class="style" @click='supp(index)'>{{item}}</li>
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
    style: 'color'
   }
 },methods:{
   valid:function(){
     this.myTabs.push(this.addToList)
    this.addToList = ''
    
   },
   supp:function(index){
    this.myTabs.splice(index,1)
   }

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
.color{
background: pink;
padding: 20px;

}
</style>
