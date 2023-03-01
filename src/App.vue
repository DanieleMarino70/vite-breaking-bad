<script>
import axios from "axios";
import AppHeader from './components/AppHeader.vue'
import AppMain from './components/AppMain.vue'

import {store} from "./data/store.js"


export default {
  data() {
    return {
      store,
    }
  },

  components: {AppHeader, AppMain},

  created(){
    axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=10&offset=0").then((response) =>{
      store.cardsList = response.data.data;
      console.log(store.cardsList);
    });
  }

}
</script>

<template>
  <AppHeader />
  <AppMain />
</template>

<style lang="scss">
@use "./assets/scss/style.scss" 

</style>
