<template>
  <div>
    <input type="checkbox" id="todo-item" checked="false" />
    <label for="todo-item">{{ todolist }}</label>
    <button id="delete">X</button>
  </div>
</template>

<script>
export default {
  props: {
    todolist: String,
  },
};
</script>

<style scoped lang="scss">

#delete {
  margin: 10px;
  border: 0px;
  color: red;
}
</style>
