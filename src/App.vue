<template>
 <h1>To Do App</h1>
 <form @submit.prevent="addNewTodo">
   <label>Task</label>
   <input v-model="newTodo" name="newTodo">
   <button>Submit</button>
 </form>
 <ul>
  <li  v-for="(toDo,index) in toDos" :key="toDo.id" class="toDo">
    <h3 :class="{ done: toDo.done }" @click="toggleDone(toDo)">{{toDo.content}}</h3>
    <button @click="removeToDo(index)">Remove Todo</button>
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
      toDos.value.push({id: Date.now(), done: false, content: newTodo.value})
      newTodo.value = ''
    }
    function toggleDone(toDo){
      toDo.done = !toDo.done
    }
    function removeToDo(index){
      toDos.value.splice(index,1)
    }
    return {
      toggleDone,
      toDos,
      newTodo,
      addNewTodo,
      removeToDo
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
.toDo {
  cursor: pointer;
}
.done {
  text-decoration: line-through;
}
</style>
