<template>
  <header class="main">
    <h1 class="logo">To Do List</h1>
    <div id="clock">
      <v-icon small></v-icon> {{ date }}
      <br />
      <v-icon small></v-icon> {{ time }}
    </div>
    <div class="list">
     <notebox todolist="Study"></notebox>
     <notebox todolist="Class"></notebox>
     <notebox todolist="Dinner"></notebox>
    <TodoCreator class="todo-app__creator"></TodoCreator>
    </div>
  </header>
</template>

<script>
// @ is an alias to /src
import notebox from "@/components/notebox.vue";
import TodoCreator from "@/components/TodoCreator.vue";
export default {
  name: "Home",
  components: {
    TodoCreator,
    notebox,
  },
  data() {
    return {
      week: ["SUN", "MON", "TUE", "WED", "THU", "FRI", "SAT"],
      time: "",
      date: "",
    };
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

.logo{
  font-size: 50px;
  font-weight: 300;
}

.list{
  border: 2px solid gray;
  width: 300px;
  background-color: #87d6b2;
  padding: 20px;
  margin: 20px;
  border-radius: 5px;
}

.main{
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

</style>
