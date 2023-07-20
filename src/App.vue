<template>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <div id="container">
      <img id="logo" src="https://media.istockphoto.com/id/1348200222/pt/vetorial/head-of-athena-goddess-symbol-vector-illustration-on-dark-background.jpg?s=612x612&w=0&k=20&c=1VxCU57x-b7oZ-mbkc9CPZ2XhPkW48Wo9rJx8_XrJKc=" width="30%" height="50%"/>
      <h1 class="text">Athena Academy</h1>
      <h2 class="text">In Athena we trust</h2>
      <p class="text">Deroncio</p>
      <p class="text">Hugão</p>
      <p class="text">Adriano</p>
      <p class="text">Gabriel</p>
      <p class="text">Luciano</p>
      <p class="text">Anderson</p>
      <p class="text">Carlos</p>
      <p class="text">Caio &nbsp; <i class="fa-solid fa-heart" style="color: #ff0000;"></i></p>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import HelloWorld from './components/HelloWorld.vue';

@Options({
  components: {
    HelloWorld,
  },
})
export default class App extends Vue {}
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

body
  {
      background-color: #141323;
  }

#container
  {
      margin-left: auto;
      vertical-align: middle;
      margin-right: auto;
  }

#logo
  {
      display: block;
      margin-left: auto;
      margin-right: auto;
      margin-bottom: 0;
  }

.text
  {
      font-family: helvetica;
      font-weight: bolder;
      color: #ae8f59;
      margin-left: auto;
      margin-right: auto;
      text-align: center;
  }
</style>
