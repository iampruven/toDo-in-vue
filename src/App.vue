<template>
 <h1>To Do App</h1>
 <form @submit.prevent="addNewTodo">
   <label>Task</label>
   <input v-model="newTodo" name="newTodo">
   <button>Submit</button>
 </form>
 <ul>
  <li :key="todo.id" v-for="todo in toDos">
    <h3>{{todo.content}}</h3>
  </li>
 </ul>
</template>

<script>

import { ref } from 'vue';

export default {

  setup(){
    const newTodo = ref('')
    const toDos = ref([])

    function addNewTodo(){
      toDos.value.push({id: Date.now(), done:false, content: newTodo.value})
    }
    return {
      toDos,
      newTodo,
      addNewTodo
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
</style>
