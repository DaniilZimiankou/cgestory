<template>
  <div id="UpperLayout">
          <div id="LogoP"><img id="LogoS" src="@/assets/taskioLogoP2.jpg"/></div>
          <button id="Surt"><router-link to="/"><img class="iconI" src="@/assets/icons8-salida-50.png"/></router-link></button>
        </div>
        <div id="MyRow">
          <div id="LeftLayout">
            <div id="Fbtn">
              <button class="btn btn-cont" id="BtnHome">
                <div>
                  <img class="iconI" src="@/assets/icons8-casa-64.png"/>
                </div>
                HOME <i class="fa fa-chevron-right"></i></button>
              <button class="btn btn-cont">
                <div>
                  <img class="iconI" src="@/assets/icons8-recordatorios-de-citas-64.png"/>
                </div>
                NOTIFICACIONS <i class="fa fa-chevron-right"></i></button>
            </div>
            <div class="Sbtn" id="Fnc">
              <button class="btnD btn-contF" id="BtnHome" @click="showComponentA">TASQUES <i class="fa fa-chevron-right"></i></button>
            </div>
            <div class="Sbtn" id="Snc">
              <button class="btnD btn-contS" id="BtnHome" @click="showComponentB">USUARIS <i class="fa fa-chevron-right"></i></button>
            </div>
          </div>
          <div id="ws">
            <div class="TascaUseerControlButton" v-if="currentComponent === 'ComponentA'">
            <tasca-form v-for="(tasca,i) in tascaList"
            :key="i" 
            :usuariId="tasca.usuariId"
            :tascaId="tasca.tascaId"
            :dataAlta="tasca.dataAlta"
            :dataInici="tasca.dataInici"
            :descripcio="tasca.descripcio"
            :nomTasca="tasca.nomTasca"
            :dataFinal="tasca.dataFinal"
            :estat="tasca.estat"
            :prioritat="tasca.prioritat"
            :comentari="tasca.comentari"
            ></tasca-form>
            </div>
            <div class="TascaUseerControlButton" v-if="currentComponent === 'ComponentB'">
            <usuari-form></usuari-form>
            </div>
        </div>
        </div>

        <!-- <script> 
          // function openReal(realName) {
          //     document.getElementById(realName).classList.toggle('hidden')
          // }

          let botones = document.querySelectorAll(".botonLikeOjo")
          let divs = document.querySelectorAll(".real")

          botones.forEach((b,i) =>{
          b.addEventListener("click",()=>{
              divs[i].classList.toggle("abierto")
          })
          })
      </script>
        </div> -->
</template>

<script>
import TascaForm from '@/components/tascaForm.vue';
import UsuariForm from '@/components/usuariForm.vue';
export default {
  name: 'HomeView',
  components: {TascaForm,UsuariForm},

  data() {
    return {
      currentComponent: '',
      tascaList: {},
      tascaTreballador: {},
      usuariRole: {}
    }
  },
  methods: {
    getPelicula(){
      axios.get("https://taskio.daw.institutmontilivi.cat/api")
      .then(resultat => this.tascaList = resultat.data.tasques)
      .then(resultat => {
                    // Guardem les dades rebudes al model
                    this.tascaList = resultat.data.tasques
                    this.usuariRole = resultat.data.usuari

                })
    },

    showComponentA() {
      this.currentComponent = 'ComponentA'
    },
    showComponentB() {
      this.currentComponent = 'ComponentB'
    }
  }
};

</script>

<style scoped>
        .TascaUseerControlButton{
          width: 100%;
          height: 100%;
        }
        #LeftLayout{
            width: 20%;
            height: 90%;
            background-color: #61AFF7;
        }
        #UpperLayout{
            width: 100%;
            height: 10%;
            /* background-color:aqua; */
            border-bottom: solid 3px black;
            position: relative;
        }
        #LogoP{
            width: 20%;
            height: 100%;
            position: absolute;
            object-fit: cover;
        }
        #LogoS{
          object-fit: cover;
          width: 100%;
          height: 100%;
        }
        #MyRow{
          display: flex;
          height: 100%;
          width: 100%;
        }
        #ws{
          width: 80%;
          height: 90%;
          background-color: #EAF9FF;
          overflow: auto;
        }
        #Fbtn{
          height: 30%;
          width: 100%;
          background-color: #0836C1;
          border-bottom: solid 3px black;
        }
        .Sbtn{
          width: 100%;
          height: 15%;
        }
        #Fnc{
          background-color: #1D6AEF;
          /* border-bottom: solid 3px black; */
        }
        #Snc{
          background-color: #3E88EF;
          /* border-bottom: solid 3px black; */
        }
        #Surt{
          margin-left: 95%;
          margin-top: 1.5%;
          position:absolute;
          cursor: pointer;
          width: 4%;
          height: 60%;
        }
        #Lletres{
          font-size: 20px;
        }
        .FbtnB{
          width: 100%;
          height: 50%;
        }

        .btn {
          width: 100%;
          height: 50%;
          font-family: "Lato";
          font-size: 2vw;
          text-transform: uppercase;
          background-color: #EAF9FF;
          font-weight: 300;
          background-color: transparent;
          transition: all 0.5s ease;
          cursor:pointer;
          padding: 0%;
        }
        .btnD {
          width: 100%;
          height: 100%;
          font-family: "Lato";
          font-size: 2vw;
          text-transform: uppercase;
          background-color: #EAF9FF;
          font-weight: 300;
          background-color: transparent;
          transition: all 0.5s ease;
          cursor:pointer;
          padding: 0%;
        }
        .btn:hover,
        button:hover {
          outline: 0;
          font-size: 2.5vw;
          color: #fff;
        }
        .btn:active,
        button:active {
          outline: 0;
          font-size: 2.5vw;
          color: #fff;
        }
        .btnD:hover,
        button:hover {
          outline: 0;
          font-size: 2.5vw;
          color: #fff;
        }
        .btnD:active,
        button:active {
          outline: 0;
          font-size: 2.5vw;
          color: #fff;
        }
        .btn-cont {
          border: none;
          color: #fff;
          background: linear-gradient(to left, #0836C1 50%, #74D0DB 50%);
          background-size: 200% 100%;
          background-position: right bottom;
        }
        .btn-contF {
          border: none;
          color: #fff;
          background: linear-gradient(to left, #1D6AEF 50%, #74D0DB 50%);
          background-size: 200% 100%;
          background-position: right bottom;
        }
        .btn-contS {
          border: none;
          color: #fff;
          background: linear-gradient(to left, #3E88EF 50%, #74D0DB 50%);
          background-size: 200% 100%;
          background-position: right bottom;
        }
        .btn-cont:hover {
          background-position: left bottom;
        }
        .btn-contF:hover {
          background-position: left bottom;
        }
        .btn-contS:hover {
          background-position: left bottom;
        }
        #BtnHome{
          border-bottom: solid 3px black;
        }
        .iconI{
          width: 3vw;
          height: 3vw;
          object-fit: cover;
        }


        /* Desplegables de ws */
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
            background-color: white;
            /* overflow-y: scroll; */
            margin: auto;
            display:block}

</style>