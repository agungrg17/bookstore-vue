<template>
  <Navbar />
  <router-view :bookList="booksData" @store="storeData" @update="updateData" @delete="deleteData" />
  <!-- <router-view @fromChild="retrieve" :fromParent="dataNama"/> -->
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue';
import Navbar from "./components/Navbar.vue";

export default {
  name: 'App',
  components: {
    // HelloWorld,
    Navbar
  },
  methods: {
    storeData(bookCreated) {
      console.log(bookCreated);
      alert("Data Berhasil Ditambahkan!");
    },
    updateData(bookChanged, bookIndex) {
      console.log(bookChanged, bookIndex);
      alert("Data Berhasil Diperbaharui!");
    },
    deleteData(book, index) {
      console.log(book);
      console.log(index);
      alert("Data Berhasil Dihapus!");
    },
  },
  data() {
    return {
      booksData: [
        {_id : 1, judul : "Laskar Pelangi", pengarang : "Andrea Hirata", harga : 80000, stok : 7},
        {_id : 2, judul : "Bumi", pengarang : "Tere Liye", harga : 85000, stok : 5 }
      ],
      // dataNama: ""
    };
  },
  // methods: {
  //   retrieve(namamu) {
  //     this.dataNama = namamu;
  //     alert("Nama Diterima: " + this.dataNama);
  //   }
  // }
};
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
