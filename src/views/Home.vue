<template>
  <header class="main">
          <h1 class="logo">To Do List</h1>
      <div id="clock">
      <v-icon small></v-icon> {{ date }}
      <br />
      <v-icon small></v-icon> {{ time }}
    </div>
    <div class="list">
      <div>
        <div id="todo"
          v-for="(content, index)  in dummyList"
          v-bind:key=index>
          <p class="text">
            {{content.text}}
          </p>
        <button id="deletebtn"  @click="deleteTodo(index)">X</button>
        </div>
      </div>
    </div>
       <div id="creator">
          <div>
            <input type="text" class="input-todo"  v-model="todo" placeholder="Enter to do"
              v-on:keyup.enter="addTodo">
           <button type="submit" @click="addTodo">add</button>
         </div>
    </div>
  </header>
</template>

<script>
// @ is an alias to /src

const dummyList = [
];

export default {
  name: "Home",
  components: {
  },
  mounted() {
    setInterval(this.updateTime, 1000); // 1초마다 시간 갱신
  },
  methods: {
    updateTime() {
      var cd = new Date();
      // 날짜 출력
      this.date =
        this.zeroPadding(cd.getFullYear(), 4) +
        "/" +
        this.zeroPadding(cd.getMonth() + 1, 2) +
        "/" +
        this.zeroPadding(cd.getDate(), 2) +
        "" +
        this.week[cd.getDay()];
      // 시간 출력
      this.time =
        this.zeroPadding(cd.getHours(), 2) +
        ":" +
        this.zeroPadding(cd.getMinutes(), 2) +
        ":" +
        this.zeroPadding(cd.getSeconds(), 2);
    },
    zeroPadding(num, digit) {
      var zero = "";
      for (var i = 0; i < digit; i++) {
        zero += "0";
      }
      return (zero + num).slice(-digit);
    },
    addTodo() {
      const todo = {
          id: 1,
          text: document.querySelector('input.input-todo').value,
      };
      if (this.todo !== "") {
        this.dummyList.push(todo);
        alert("할일 추가: " + this.todo)
      } else {
        alert("다시 입력하세요");
      }
      this.todo = "";
    },  
    deleteTodo(index) {
        this.dummyList.splice(index,1);
        console.log(index)
    }
  },
  data() {
    return {
      week: ["SUN", "MON", "TUE", "WED", "THU", "FRI", "SAT"],
      time: "",
      date: "",
      dummyList,
      todo: "",
      i: 0,
    };
  },
};
</script>
<style scoped lang="scss">
#box3 {
  width: 200px;
  background-color: "blue";
}

#clock {
  font-size: 0.875rem;
  font-weight: 500;
}

.logo {
  font-size: 50px;
  font-weight: 300;
}

#todo {
  display: flex;
  flex-direction: row;
  justify-content: center;
}
.list {
  border: 2px solid gray;
  width: 300px;
  background-color: #87d6b2;
  padding: 20px;
  margin: 20px;
  border-radius: 5px;
}

#deletebtn {
  color: red;
  width: 20px;
  font-size: 10px;
  border-radius: 50px;
  border: 1px solid lightgrey;
  padding: 3px;
  margin: 10px;
  align-items: center;
}
.main {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>
