<template>
  <div class = "main">
    <div class = "nav">
      <h1>안녕하세요</h1>
      <div id="app">
         <h1>To-Do List</h1>
          <ul>
          <li>
               <notebox></notebox>
         </li>
         </ul>
      </div>
      <div id= 'container'></div> 
    </div>
  </div>
</template>



<script>
import ToDoItem from './components/notebox.vue';

export default {
   name: 'main',
  components: {
    notebox
  }
  }
</script>


<style lang="scss" scoped>
  #container {
      width: 200px,
      background-color: blue
    }

</style>
