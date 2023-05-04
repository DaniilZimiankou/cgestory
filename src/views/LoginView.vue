<template>
    <form id="papa">
            <div id="ImatgeLogoL"><img id="ImatgeLogoK" src="@/assets/taskioLogoP2.jpg"/></div>
              <input class="LoginContrasenya" placeholder="Login">
              <input class="LoginContrasenya" placeholder="Contrasenya">
              <button><router-link to="/home">Enviar</router-link></button>
    </form>
</template>
  
  <script>
  export default {
    name: 'App',
    // components: {},
  };
  </script>
  
  <style scoped>
  #ImatgeLogoL{
          margin-top: 10%;
          width: 30%;
          height: 10%;
          /* position: absolute; */
          object-fit: cover;
        }
        #ImatgeLogoK{
          object-fit: cover;
          border-radius: 10px;
          width: 100%;
          height: 100%;
        }
        #papa{
          width: 100%;
          height: 100%;
          background-color: #EAF9FF;
          display: flex;
          align-items: center;
          flex-direction: column;
        }
        .LoginContrasenya{
          width: 30%;
          height: 10%;
          border-radius: 10px;
          background-color: white;
          margin-top: 5%;
        }
        #formLogin{
          height: 100%;
          width: 100%;
        }
  </style>