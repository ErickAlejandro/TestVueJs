<template>
  <div class="hello">
    
    <div class="content">
      <h2 class="welcomeUser">Bienvenido Usuario</h2>

      <span class="line1"></span>

      <p class="dearUser">Por favor ingresa a tu cuenta ingresando tu numero de cedula y contrasena. Si no tienes una cuenta en TodoLegal, puedes crear una gratis.</p>
      <form v-on:submit.prevent='login'>
      <input id="Cedula" v-model="message" placeholder="Cedula de Identidad" required>
      <br>
      <input id="password" v-model="password" type="password" placeholder="Contrasena" >
      <br>
      <br>
      <a id="createAccount" href="#">No tengo cuenta, crear una GRATIS.</a>
      <br>
      <router-link id="continue" to="/about" active-class="isDisable" > <button id="continue" :disabled="isDisable">CONTINUAR</button> </router-link>
      </form>

    </div>

    <p id="autor">Examen by <a id="dir" href="https://todolegal.com/">TodoLegal</a></p>
    
  </div>
</template>


<script>

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },

  computed:{
    
    isDisable () {
      return !this.message && !this.password
    }
  },

  data (){
    return {
      message: null,
      password: null
    }
  },

  users (){
    return {
      message: '',
      password: '',
      error: false,
      error_msg: ''
    }
  },

  methods: {
    login() {
      console.log(this.message)
    }
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped src="./style.css"></style>
<style>
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@700&display=swap');
</style>

