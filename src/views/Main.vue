<template>
  <div class="main">
    <div class="nav">
      <h1>안녕하세요</h1>
      <div id="app">
        <h1>To-Do List</h1>
        <ul>
          <li>
            <NoteBox></NoteBox>
          </li>
        </ul>
      </div>
      <div id="container"></div>
    </div>
  </div>
</template>

<script>
import NoteBox from "../components/NoteBox.vue";

export default {
  name: "main",
  components: {
    NoteBox,
  },
};
</script>

<style lang="scss" scoped>
#container {
  width: 200px;
  background-color: blue;
}
</style>
