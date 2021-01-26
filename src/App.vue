<template>
  <div id="app">
    <Header v-on:changePeople="changePeople"></Header>
    <main>
      <p>People List</p>
      <article v-if="!selectedPeople">
        <People v-for="(people, index) in peoples" :key="people.id" v-bind:people="people" v-bind:index="index"></People>
      </article>
      <article v-else>
        <People v-bind:people="selectedPeople" v-bind:index="0"></People>
      </article>
    </main>
    <Footer></Footer>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import People from './components/People.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    Header,
    People,
    Footer
  },
  data: function () {
    return {
      peoples:[
        {
          id: 1,
          name: "awan",
          genre: "Laki-laki",
          image: "nasa.png"
        },
        {
          id: 2,
          name: "Bintang",
          genre: "Perempuan",
          image: "miku.jpg"
        },
      ],
      selectedPeople: ''
    }
  },
  methods: {
    changePeople: function(){
      this.selectedPeople = this.randomPeople()
    },
    randomPeople(){
      return this.peoples[Math.floor(Math.random() * this.peoples.length)]
    }

  }
  
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
article{
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  text-align: center;
}
</style>