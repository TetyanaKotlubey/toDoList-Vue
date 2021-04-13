<template>
  <div>
    <h2>My ToDoList</h2>
   <AddToDo v-on:add-todo="addToDo"/>
    <ul>
        <li v-bind:key="todo.id" v-for="todo in todos">
        <ToDo v-bind:todo="todo"  @set-completed="$value => { todo.completed = $value }" v-on:delete="deleteTodo"/>
        </li>
    </ul>
  </div>
</template>
<script>

import ToDo from './ToDo';
import AddToDo from './AddToDo';
export default {
  name: 'ToDoApp',
  components: {
    ToDo,
    AddToDo
  },
    data() {
    return {
      todos: [
        
      ],
    }
  },
    methods:
    {
      addToDo (newToDoObj)
      {
        this.todos = [...this.todos, newToDoObj];
      },
      deleteTodo (index)
      {
          this.todos.splice(index, 1);
      }
    
    }
    
}
</script>
<style  scoped lang="css">
h2 {
  font-weight: 800;
  letter-spacing: 5px;
  color: #DAA520;
  font-size: 30px;
  text-transform: uppercase;
}
ul 
{
    list-style-type: none;
    padding: 0;
}
 

</style>