<template>
    <!-- <div class="linkRespB1">
              <div class="resBusqd1"></div>
              <button class="botonLikeOjo1">
                  <img src="images/ojo_blanco.png" >
              </button>
              <div class="botonLikeOjoR1"></div>
          </div>
          <div class="real1"></div> -->

              <div class="linkRespB1">
                  <div class="resBusqd1"></div>
                  <button class="botonLikeOjo1">
                      <img src="images/ojo_blanco.png" >
                  </button>
                  <div class="botonLikeOjoR1"></div>
              </div>
              <div class="real1">
                  <div>Usuari ID: <input id="tascaInput" v-model="usuariId"> </div>
                  <div>ID tasca: <input id="tascaInput" v-model="tascaId"></div>
                  <div>Data alta: <input id="tascaInput" v-model="dataAlta"></div>
                  <div>Data inici: <input id="tascaInput" v-model="dataInici"></div>
                  <div>Descripcio: <input id="tascaInput" v-model="descripcio"></div>
                  <div>Nom tasca: <input id="tascaInput" v-model="nomTasca"></div>
                  <div>Data final: <input id="tascaInput" v-model="dataFinal"></div>
                  <div>Estat: <input id="tascaInput" v-model="estat"></div>
                  <div>Prioritat: <input id="tascaInput" v-model="prioritat"></div>
                  <div>Comentari: <input id="tascaInput" v-model="comentari"></div>
              </div>
              <button id="guardarTasca">Guardar</button>
</template>

<script>
export default {
  name: 'tascaForm',
  props:["usuariId", "tascaId", "dataAlta", "dataInici", "descripcio", "nomTasca", "dataFinal", "estat", "prioritat", "comentari"],

  mounted(){
          let botones = document.querySelectorAll(".botonLikeOjo1")
          let divs = document.querySelectorAll(".real1")

          botones.forEach((b,i) =>{
          b.addEventListener("click",()=>{
              divs[i].classList.toggle("abierto1")
          })
          })
  }
};
</script>

<style>
.tascaMain1{
            width: 90%;
            height: 10%;
            border-radius: 10px;
            background-color: white;
        }

        /* Desplegable */
        .linkRespB1{
            margin: 10px auto;
            width: 90%;
            height: 8%;
            border: 2px solid #8360c3;
            border-radius: 8px;
            display: flex;
            flex-direction: row;
            align-items: center;
            background-color: white;
        }
        .resBusqd1{
            width: 89%;
            height: 90%;
            margin: 4px;
        }
        .botonLikeOjo1{
            width: 4%;
            height: 90%;
            margin: 4px;
            border-radius: 50%;
            background-color:#8360c3;
            display: flex;
            align-items: center;
            overflow: hidden;
            justify-content: center;
        }

        .botonLikeOjoR1{
            width: 4%;
            height: 90%;
            margin: 4px;
            border-radius: 50%;
            background-color:#8360c3;
            display: flex;
            align-items: center;
            overflow: hidden;
            justify-content: center;
        }
        .real1{
            /* border: 1px solid #333333;
            width: 80%;
            height: 100px; */
            /* overflow-y: scroll; */
            display: none;
        }
        .real1.abierto1{
            border: 1px solid #333333;
            width: 90%;
            height: 50%;
            border-radius: 8px;
            background-color: white;
            /* overflow-y: scroll; */
            margin: auto;
            display:block}
</style>