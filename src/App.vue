<template>
  <div id="app">
    <Header />
    <AddTodo v-on:add-todo="addTodo" />
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
import Header from './components/layout/Header';
import Todos from './components/Todos';
import AddTodo from './components/AddTodo';


export default {
  name: 'app',
  components: {
    Header,
    Todos,
    AddTodo
  },
  data() {
    return{
      todos: [
        {
          id: 1,
          title: "Airpods Pro",
          beschrijfing: "Beter geluids kwaliteid",
          prijs: "230",
          foto: "https://s.s-bol.com/imgbase0/imagebase3/large/FC/7/4/1/9/9200000123229147.jpg",
          completed: false
        },
        {
          id: 2,
          title: "Nieuwe auto",
          beschrijfing: "Zodat ik rond kan rijden",
          prijs: "1000",
          foto: "https://autorai.nl/wp-content/uploads/2017/06/Volkswagen-Polo-2018-1600-03-640x480.jpg",
          completed: false
        },
        {
          id: 3,
          title: "Iphone 11",
          beschrijfing: "Nieuwe telefoon, oude is kapot",
          prijs: "1600",
          foto: "https://www02.cp-static.com/objects/high_pic/7/764/1351040479_smartphones-apple-iphone-11-64-gb-black-mwlt2zd-a.jpg",
          completed: false
        },
        {
          id: 4,
          title: "Chocola",
          beschrijfing: "Heel erg lekker",
          prijs: "5",
          foto: "https://sugarfreelondoner.com/wp-content/uploads/2019/05/keto-milk-chocolate.jpg",
          completed: false
        }
      ]
    }
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    addTodo(newTodo) {
      this.todos = [...this.todos, newTodo];
    }
  }
}
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}

.btn{
  display: inline-block;
  border: none;
  background: #E10A0A;
  color: #fff;
  padding: 7px 20px;
  cursor: pointer;
}

.btn:hover{
  background: #E83E3E;
}

#app {
  text-align: center;
}
</style>
