<template>
 <Zoom/>
  
</template>

<script>
import Zoom from './components/Zoom'
//import MiPrimerComponente from '@/components/MiPrimerComponente'



export default {
  name: 'App',
  components: {
    Zoom
    //MiPrimerComponente
  },
  data() {
    return {
      miTitulo: "Titulo mio"
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
