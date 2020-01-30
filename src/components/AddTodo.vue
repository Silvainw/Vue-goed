<template>
  <div>
    <form @submit="addTodo">
      <input type="text" v-model="title" name="title" placeholder="Voeg nieuwe wens toe...">
      <input type="text" v-model="prijs" name="prijs" placeholder="Prijs">
      <input type="submit" value="Submit" class="btn">
    </form>
  </div>
</template>

<script>
  import uuid from 'uuid';
  export default {
    name: "AddTodo",
    data() {
      return {
        title: '',
        prijs: ''
      }
    },
    methods: {
      addTodo(e) {
        e.preventDefault();
        const newTodo = {
          id: uuid.v4(),
          title: this.title,
          prijs: this.prijs,
          completed: false
        }
        //send up to parent
        this.$emit('add-todo', newTodo);

        this.title = '';
        this.prijs= '';
      }
    }
  }
</script>

<style scoped>
  form{
    display: flex;
  }

  input[type="text"] {
    flex: 10;
    padding: 5px;
  }

  input[type="submit"] {
    flex: 2;
  }
</style>
