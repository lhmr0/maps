<template>
<section class="hero is-dark is-large">
<div class="hero-body is-mobile">
    <div class="container">
        <center><gmap-map
    :center="center"
    :zoom="15"
    style="width: 70%px; height: 400px"
  >
  <gmap-polygon :paths="paths">
      </gmap-polygon>
    <gmap-marker
      :key="index"
      v-for="(m, index) in markers"
      :position="m.position"
      :clickable="true"
      :draggable="true"
      @click="center=m.position"
    ></gmap-marker>
  </gmap-map></center>  
  <center>
      <h2 class="subtitle">
        Reporta tus incidentes</h2>
        <button class="button is-danger is-medium"
            @click="isModalActive = true">
            Reportar incidente
        </button>
        <b-modal :active.sync="isModalActive" :width="moda">
            <form action="">
              <div class="modal-card">
                  <header class="modal-card-head">
                      <p class="modal-card-title">Reportar incidente</p>
                  </header>
                  <section class="modal-card-body">
                      <b-field label="Titulo">
                          <b-input
                              type="text"
                              v-model="titulo"
                              placeholder="Titulo del incidente"
                              required>
                          </b-input>
                      </b-field>

                  <b-field>
                  <b-radio-button v-model="radioButton"
                      native-value="Robo"
                      type="is-danger">
                      <span>Robo</span>
                  </b-radio-button>

                  <b-radio-button v-model="radioButton"
                      native-value="Secuestro"
                      type="is-danger">
                      <span>Secuestro</span>
                  </b-radio-button>

                  <b-radio-button v-model="radioButton"
                      native-value="Pelea"
                      type="is-danger">
                      Pelea
                  </b-radio-button>
                  <b-radio-button v-model="radioButton"
                      native-value="Asesinato"
                      type="is-danger">
                      Asesinato
                  </b-radio-button>
                  <p class="content nigru">
                    <b> Seleccion:</b>
            {{ radioButton }}
              </p>
                  </b-field>     
                 <b-field label="Descripcion">
                    <b-input
                        type="text"
                        v-model="desc"
                        placeholder="Descripcion del incidente"
                        required>
                    </b-input>
                </b-field>

                
            </section>
            <footer class="modal-card-foot">           
                <button class="button" type="button">Cerrar</button>
                <button class="button is-primary">Enviar</button>
            </footer>
        </div>
    </form>
        </b-modal>
  </center>    
    </div>
  </div>
  
</section>
</template>



 

<script>  
  export default {


     components: {
           
        },
       data () {
          return {        
            center: {lat: -8.1285196, lng: -79.0278064},        
            markers: [{
              position: {lat: -8.1274836, lng: -79.0319926}
            }, {
              position: {lat: -8.1288996, lng: -79.0312268}
            }, {
              position: {lat: -8.1285196, lng: -79.0278064}
            }], 
              paths: [
                        [ {lat: -8.125, lng: -79.0250}, {lat: -8.1235196, lng: -79.035}, {lat: -8.130, lng: -79.035}, {lat: -8.130, lng: -79.025} ],
                      ],
           isModalActive: false,
                isModalActive: false,
                radioButton: '',
                titulo:'',
                desc:'',
                moda:'80%',
           
          }
        }
      }
</script>


<style scoped>
  .nigru {
   color:black;  
  }
   .modal-card {
        width: auto;
    }
</style>
