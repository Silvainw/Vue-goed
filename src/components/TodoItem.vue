<template>
  <div class="todo-item" v-bind:class=" {'is-complete':todo.completed}">
    <p>
      <input type="checkbox" v-on:change="markComplete">
      {{todo.title}},<br>
      {{todo.beschrijfing}}.<br>
      <img :src="todo.foto" :alt="todo.title"><br>
      € {{todo.prijs}}.
      <button @click="$emit('del-todo', todo.id)" class="del">x</button>
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
    padding: 5px 9px;
    border-radius: 50%;
    cursor: pointer;
    float: right;
  }

  img {
    width: 10%;
    height: 10%;
  }
</style>
