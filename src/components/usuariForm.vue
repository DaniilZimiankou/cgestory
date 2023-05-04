<template>
    <div class="linkRespB">
              <div class="resBusqd"></div>
              <button class="botonLikeOjo">
                  <img src="images/ojo_blanco.png" >
              </button>
              <div class="botonLikeOjoR"></div>
          </div>
          <div class="real"></div>

              <div class="linkRespB">
                  <div class="resBusqd"></div>
                  <button class="botonLikeOjo">
                      <img src="images/ojo_blanco.png" >
                  </button>
                  <div class="botonLikeOjoR"></div>
              </div>
              <div class="real">
                  <p> </p>
                  <p>Autor: </p>
                  <p>Categoria: </p>
                  <p>Descripcion: </p>
              </div>
</template>

<script>
export default {
  name: 'usuariForm',
  props:[],

  mounted(){
          let botones = document.querySelectorAll(".botonLikeOjo")
          let divs = document.querySelectorAll(".real")

          botones.forEach((b,i) =>{
          b.addEventListener("click",()=>{
              divs[i].classList.toggle("abierto")
          })
          })
  }
};
</script>

<style>
.tascaMain{
            width: 90%;
            height: 10%;
            border-radius: 10px;
            background-color: white;
        }

        /* Desplegable */
        .linkRespB{
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
        .resBusqd{
            width: 89%;
            height: 90%;
            margin: 4px;
        }
        .botonLikeOjo{
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

        .botonLikeOjoR{
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
        .real{
            /* border: 1px solid #333333;
            width: 80%;
            height: 100px; */
            /* overflow-y: scroll; */
            display: none;
        }
        .real.abierto{
            border: 1px solid #333333;
            width: 90%;
            height: 50%;
            border-radius: 8px;
            background-color: purple;
            /* overflow-y: scroll; */
            margin: auto;
            display:block}
</style>