<template>
  <div>
    <form @submit="addVerlang">
      <input type="text" v-model="title" name="title" placeholder="Voeg nieuwe wens toe..." class="kleur">
      <input type="text" v-model="prijs" name="prijs" placeholder="Prijs" class="kleur">
      <input type="text" v-model="beschrijfing" name="beschrijfing" placeholder="Beschrijfing" class="kleur">
      <input type="text" v-model="foto" name="foto" placeholder="Link Foto" class="kleur">
      <input type="submit" value="Submit" class="btn">
    </form>
  </div>
</template>

<script>
  import uuid from 'uuid';
  export default {
    name: "AddVerlang",
    data() {
      return {
        title: '',
        prijs: '',
        beschrijfing: '',
        foto: ''
      }
    },
    methods: {
      addVerlang(e) {
        e.preventDefault();
        const newVerlang = {
          id: uuid.v4(),
          title: this.title,
          prijs: this.prijs,
          beschrijfing: this.beschrijfing,
          foto: this.foto,
          completed: false
        }
        //send up to parent
        this.$emit('add-verlang', newVerlang);

        this.title = '';
        this.prijs= '';
        this.beschrijfing= '';
        this.foto= ''
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

  .kleur {
    background-color: #FEE8E8;
  }
</style>
