<template>
<!-- !!! Component 1 = props paprent à enfant !!!-->
<!-- !!! Component 2 = props enfant  à parent !!!-->

  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <!--Utilisation du component -->
    <Component1 />
    <!--Utilisation du component avec des props-->
    <Component1 userName="Andy" />
    <!--Utilisation du component avec des props venant d'une variable du parent-->
    <Component1 :userName='secondUserName' />
    <!--Utilisation du 2e component. on y ajoute @changeName qui est l'event créé dans l'enfant. Il est égal à 'update' qui est la methode qui recupere la variable de l'enfant via son paramètre value  -->

    <Component2 @changeName='update' />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
// import du component1
import Component1 from './components/Component1.vue'
import Component2 from './components/Component2.vue'

export default {
  name: 'App',
  // appel du component 1
  components: {
    HelloWorld,Component1,Component2
  },
  data() {
    return {
      secondUserName: 'KevVar'
    }
  },
  methods: {
    update(value){
      console.log(value)
      this.secondUserName = value;

    }
  },
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
</style>
