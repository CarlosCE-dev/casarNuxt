<template>
  <div>
     
    <h3> Numero de intentos {{ intentos }}</h3>
    <v-card class="card blue lighten-4" width="200px" height="286px" :style="`top:${ top };left:${ left}`" >
        <v-card-text class="text-center black--text">
          <v-avatar class="profile" color="grey" size="128" tile>
            <v-img src="https://cdn.vuetifyjs.com/images/profiles/marcus.jpg"></v-img>
          </v-avatar>
          <div class="pt-2">
            Haz click para obligar a Carlos que se case contigo owo
          </div>
        </v-card-text>
        <v-card-actions>
          <v-btn color="primary" class="btn" @click="hover" :ripple="false" block>
            Boton
          </v-btn>
        </v-card-actions>
    </v-card>

  </div>
</template>

<script>
  export default {
    data: () => ({
      intentos: 0,
      top: '20px',
      left: '30px'
    }),
    methods: {
      hover() {

          const h = document.documentElement.scrollHeight - 286;
          const w = document.documentElement.scrollWidth - 200;
          
          
          this.top = `${ Math.floor( Math.random() * h ) }px`;
          this.left = `${ Math.floor( Math.random() * w ) }px`;
          this.intentos++
      }
    },
  }
</script>

<style scoped>
.card{
  position:fixed;
}
.intentos{
  position: absolute;
};
.full-height{
  height: 100%;
}
.btn .v-btn::before{
  background-color: transparent;
}

</style>