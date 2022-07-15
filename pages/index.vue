<template>
  <div>
      <div>
          <section class="section">
            <header>
               <img class="header-img" src="images/header.png" alt="">
            </header>
            
            <div class="columns is-vcentered">
              <div class="column ">
                
                <Timetables/>


              </div>
              <div class="column">
                <h1 class="title is-3">
                  Geolocalización en tiempo real del autobús al Aeropuerto de Murcia
                </h1>
                
                <real-time-map
                  :centerAlways="centerAlways"
                  :showTrail="showTrail"
                  />

                <b-field class="mt-5 has-text-white has-text-bold" >
                    <b-switch type="is-success" v-model="centerAlways">Centrar siempre</b-switch>
                </b-field>
                <b-field class="mt-5 has-text-white has-text-bold" >
                    <b-switch type="is-success" v-model="showTrail">Mostrar estela</b-switch>
                </b-field>

              </div>
            </div>

          </section>
      </div>
     
      
  </div>
</template>

<script>
export default {
  data(){
    return {
      centerAlways: false,
      showTrail: true
    }
  }
}
</script>



<style>
  body{
    background: #01395E;
    min-height: 100%;
    width: 100%;
    position: absolute;
  }

  header{
    text-align: center;
  }
  header img{
    display: inline-block;
    margin-bottom: 8vh;
    width: 33%;
  }

  .title{
    color: white;
  }

  .subtitle{
    color: white;
    text-decoration: underline;
  }


@media (max-width: 600px) {
  header img{
    width: 500px;
  }
}
  
</style>
