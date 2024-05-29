<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import store from './Data/store.js'

export default {
  components: {
    AppHeader,
    AppMain,

  },
  data() {
    return {
      store
    }
  },
  methods: {

  },
  created() {
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=30&offset=0').then(risultato => {
      // console.log(risultato.data.data)
      this.store.carte = risultato.data.data
    })
  },
  mounted() {

  }
}
</script>

<template>
  <header>
    <AppHeader />
  </header>

  <main>
    <AppMain />
  </main>


</template>

<style scoped></style>
