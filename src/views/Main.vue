<template>
  <div class="main">
    <div class="nav">
      <div id="app">
        <h1>To-Do List</h1>
        <div>
          <div
            class="list"
            v-for="i in dummyList"
            v-bind:key="i.id"
            >
            <p class="todo">{{ i.content }}</p>
            <button type="submit" class="delete" @click="deleteG(i.id)">-</button>
          </div>
        </div>

        <input
          type="text"
          class="creator"
          v-model="todo"
          placeholder="입력하세요"
          v-on:keyup.enter="add"
          />
        <button type="submit" @click="add">+</button>
      </div>
      <div id="container"></div>
    </div>
  </div>
</template>

<script>
//import NoteBox from "../components/NoteBox.vue";

const dummyList = [
  { 
    id : 0,
    content : "Hello"
  }
];
export default {
  name: "main",
  components: {},
  methods: {
    add() {
      const todo = {
        id: 1,
        content: this.todo,
      };
      this.dummyList.push(todo);
    },
    deleteG(index) {
      console.log(this.dummyList);
      this.dummyList.splice(index,1);
      console.log(this.dummyList);
    }
  },
  data() {
    return {
      dummyList,
    };
  },
};
</script>

<style lang="scss" scoped>
#container {
  width: 200px;
  background-color: blue;
}

.list {
  width : 200px;
  border: 1px solid gray;
}

.main{
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items : center;
}
</style>
