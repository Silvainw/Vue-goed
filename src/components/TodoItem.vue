<template>
  <div class="todo-item" v-bind:class=" {'is-complete':todo.completed}">
    <p> <br>
      <input type="checkbox" v-on:change="markComplete"> Gekocht. <br>
      <br>{{todo.title}},<br>
      {{todo.beschrijfing}}.<br>
      <img :src="todo.foto" :alt="todo.title"><br>
      € {{todo.prijs}}.<br>
      <button @click="$emit('del-todo', todo.id)" class="del">Verwijder</button><br>
    </p>
  </div>
</template>

<script>
  export default {
    name: "TodoItem",
    props: ["todo"],
    methods: {
      markComplete() {
        this.todo.completed = !this.todo.completed;
      }
    }
  }
</script>

<style scoped>
  .todo-item {
    background: #F7D4D4;
    padding: 10px;
    border-bottom: 1px #000 solid;
  }

  .is-complete {
    text-decoration: line-through;
  }

  .del {
    background: #ff0000;
    color: #fff;
    border: none;
    padding: 5px 60px;
    margin-right: 44%;
    border-radius: 5%;
    cursor: pointer;
    float: right;
  }

  img {
    width: 10%;
    height: 10%;
  }
</style>
