<template>
 <div id="app">
   <ToDoApp v-bind:todos="todos" v-on:delete-todo="deleteTodo"/>
 </div>
</template>

<script>
import ToDoApp from './components/ToDoApp';

export default {
  name: 'App',
  components: 
  {
    ToDoApp
  },
  
  
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Nunito:wght@400;600;700;800&display=swap');
body 
{
  background-color: #F9BDBD;
  box-sizing: border-box;
  text-align: center;
  font: 400 20px 'Nunito', sans-serif;
  color: #501d43;

}

</style>
