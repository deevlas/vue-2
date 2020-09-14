<template>
  <div id="app">
    <addToDo :toDoArr="toDoArr" @addToDoApp="addToDoList" />
    <todolist :toDoArr="toDoArr" @removeToDoApp="remToDo" />
  </div>
</template>

<script>
import todolist from "./components/todo/todolist";
import addToDo from "./components/todo/addToDo";

export default {
  name: "App",

  data() {
    return {
      toDoArr: []
    };
  },

  components: {
    addToDo,
    todolist
  },

  methods: {
    remToDo(index) {
      this.toDoArr.splice(index, 1);
    },
    addToDoList(txt) {
      if (txt.length > 0) {
        this.toDoArr.push(txt);
      }
    }
  }
};
</script>

<style>
</style>