<template>
  <div id="app">
    <Header />
    <AddVerlang v-on:add-verlang="addVerlang" />
    <Verlangen v-bind:verlangen="verlangen" v-on:del-verlang="deleteVerlang" />
  </div>
</template>

<script>
import Header from './components/layout/Header';
import Verlangen from './components/Verlangen';
import AddVerlang from './components/AddVerlang';


export default {
  name: 'app',
  components: {
    Header,
    Verlangen,
    AddVerlang
  },
  data() {
    return{
      verlangen: [
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
    deleteVerlang(id) {
      this.verlangen = this.verlangen.filter(verlang => verlang.id !== id);
    },
    addVerlangen(newVerlang) {
      this.verlangen = [...this.verlangen, newVerlang];
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
