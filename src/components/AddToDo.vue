<template>
  <div>
    <form @submit="addToDo">
      <input type="text" v-model="title" name="title">
      <button type="submit">Add</button>
    </form>
  </div>
</template>
<script>
// import uuid from 'uuid';
import {v4} from 'uuid';
const uuId = v4()
export default {
  name: 'AddToDo',
  data() {
    return {
      title: ''
    }
  },
  methods: {
    addToDo(e) {
      e.preventDefault();
      const newToDoObj = {
        id:uuId,
        title: this.title,
        completed: false
      }
      this.$emit('add-todo', newToDoObj);
      this.title = '';
    }
  }
}
</script>
<style scoped>
input 
{
        background-color: transparent;
        border: 2px solid hsla(0,0%,100%,.35);
        color: inherit;
            box-shadow: none;
         outline: none;
         padding-left: 12px;
         padding-right: 12px;
         border-radius: 6px;
         font-size: 18px;
         margin-top: 6px;
         margin-bottom: 12px;
}
button {

   
    box-shadow: none;
    outline: none;
    padding: 8px 10px;
    border: none;
    border-radius: 5px;
    background-color: #A8DCEC;
    border: 1px solid #F9BDBD;
    font-size: 12px;
   font-family: 'Nunito';
   font-weight: 700;
   margin-left: 10px;
				
	}
</style>