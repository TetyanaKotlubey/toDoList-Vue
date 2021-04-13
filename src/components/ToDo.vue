<template>
  <div v-bind:class="{'is-completed':todo.completed}">
    <input type="checkbox" @change="markCompleted" id="check"/>
    <p>{{ todo.title }}</p>
   <button @click="deleteTodo(todo.id)">Delete</button>
  </div>
</template>
<script>
export default {
  name: 'ToDo',
  props: ["todo"],
   methods: {
    markCompleted() {
        if(!document.getElementById('check').checked)
      {
          this.$emit('set-completed', false)
          }
        else
        {
            this.$emit('set-completed', true)
        }
        
    },
    deleteTodo(index)
    {
        this.$emit('delete', index);
    }
    
  },
  
}
</script>
<style scoped>
div 
{
    display: flex;
    justify-content: center;
    padding: 10px;
    margin: 0 auto;

    align-items: center;
}
p 
{
    margin: 0 15px 0 0;
}
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
         margin: 0;
        margin-right: 5px;
}
button {

   
    box-shadow: none;
    outline: none;
    padding: 5px 10px;
    border: none;
    background-color: #A8DCEC;
    border: 1px solid #F9BDBD;
    font-size: 12px;
   
				
	}
.is-completed
{
    text-decoration: line-through;
}

</style>