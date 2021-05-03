<template>
  <div>
    <input type="checkbox" id="todo-item" checked="false" />
    <label for="todo-item">{{ todolist }}</label>
  </div>
</template>

<script>
export default {
  props: {
    todolist: String,
  },
};
</script>
