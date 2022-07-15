<template>
  <div>
      <div>
          <section class="section">
            <header>
               <img class="header-img" src="images/header.png" alt="imagen corporativa linea bus aeropuerto murcia">
            </header>
            
            <div class="columns is-vcentered">
              <div class="column ">
                
                <Timetables/>


                <center>

                <div>
                  <a href="https://cutt.ly/TLPwj8h" target="_blank">
                    <b-button type="is-danger" size="is-large"
                        icon-left="bus-multiple">
                        Comprar billetes
                    </b-button>
                  </a>
                </div>

                
                <span class="has-text-white help">Se te redirigirá a la web oficial de Interbus (operadora)</span>

                </center>


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

      <footer class="footer">
        <div class="content has-text-centered">
          <p>
            Desarrollado con ❤️ por <a href="https://github.com/youngsdeveloper" target="_blank">Enrique Rodríguez López</a>.
          </p>
          <p>
            El código fuente está disponible en <a href="https://github.com/youngsdeveloper/aeropuerto-bus-realtime" target="_blank">GitHub</a>
          </p>
        </div>
      </footer>
     
      
  </div>
</template>

<script>
export default {
  data(){
    return {
      centerAlways: false,
      showTrail: true,


      pageTitle: "Bus al Aeropuerto de Murcia - Horarios en tiempo real.",
      pageURL: "https://youngsdeveloper.github.io/aeropuerto-bus-realtime/",
      description: 'Horarios del autobus entre el Aeropuerto de la Región de Murcia y Murcia y Cartagena. Posición en tiempo real.',
      ogImage: "https://youngsdeveloper.github.io/aeropuerto-bus-realtime/images/header.png"
    }
  },

  head() {
      return {
        title: this.pageTitle,
        meta: [
          {
            hid: 'description',
            name: 'description',
            content: this.description
          },
          
          
          { hid: 'og:title', property: 'og:title', content: this.pageTitle },
          { hid: 'og:url', property: 'og:url', content: this.pageUrl },
          { hid: 'og:description', property: 'og:description', content: this.description },
          { hid: 'og:image', property: 'og:image', content: this.ogImage},
          
          // twitter card
          { hid: "twitter:title", name: "twitter:title", content: this.pageTitle },
          { hid: "twitter:url", name: "twitter:url", content: this.pageUrl },
          { hid: 'twitter:description', name: 'twitter:description', content: this.description },
          { hid: "twitter:image", name: "twitter:image", content: this.ogImage},

        ],
        link: [
          { rel: 'icon', type: 'image/x-icon', href: '/images/favicon.png' }
        ]
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
    zoom: 0.8;
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


  .help{
    margin-top: 10px;
    font-size: 0.9em;
  }


@media (max-width: 600px) {
  header img{
    width: 500px;
  }
}
  
</style>
