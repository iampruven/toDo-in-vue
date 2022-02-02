<template>
 <h1>To Do App</h1>
 <form @submit.prevent="addNewTodo">
   <label>Task</label>
   <input name="newTodo">
   <button>Submit</button>
 </form>
 <!-- <h3></h3> -->
</template>

<script>


export default {
  
  setup(){

    function addNewTodo(){
      console.log("hello")
    }
    return {addNewTodo}
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
</style>
