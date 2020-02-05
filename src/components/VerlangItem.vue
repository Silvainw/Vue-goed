<template>
  <div class="verlang-item" v-bind:class=" {'is-complete':verlang.completed}">
    <p> <br>
      <input type="checkbox" v-on:change="markComplete"> Gekocht. <br>
      <br>{{verlang.title}},<br>
      {{verlang.beschrijfing}}.<br>
      <img :src="verlang.foto" :alt="verlang.title"><br>
      € {{verlang.prijs}}.<br>
      <button @click="$emit('del-verlang', verlang.id)" class="del">Verwijder</button><br>
    </p>
  </div>
</template>

<script>
  export default {
    name: "VerlangItem",
    props: ["verlang"],
    methods: {
      markComplete() {
        this.verlang.completed = !this.verlang.completed;
      }
    }
  }
</script>

<style scoped>
  .verlang-item {
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
