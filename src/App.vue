<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import store from './Data/store.js';

export default {
  components: {
    AppHeader,
    AppMain,
  },
  data() {
    return {
      store,
      selectedArchetype: '',
    };
  },
  computed: {
    filteredCards() {
      if (this.selectedArchetype) {
        return this.store.carte.filter(carta => carta.archetype === this.selectedArchetype);
      } else {
        return [];
      }
    },
  },
  created() {
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=30&offset=0').then(risultato => {
      console.log(risultato.data.data);
      this.store.carte = risultato.data.data;
    });
    axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php').then(risultatoArch => {
      this.store.archetypes = risultatoArch.data;
    });
  },
}
</script>

<template>
  <header>
    <AppHeader />
  </header>

  <main>
    <div class="selector">
      <label for="archtype-select">Choose an archetype:</label>
      <br>
      <select name="archetypes" id="archtype-select" v-model="selectedArchetype">
        <option value="">--Please choose an archetype--</option>
        <option v-for="archetipo in store.archetypes" :key="archetipo.archetype_name" :value="archetipo.archetype_name">
          {{ archetipo.archetype_name }}
        </option>
      </select>
    </div>
    <AppMain :filteredCards="filteredCards" />
  </main>
</template>

<style scoped>
.selector {
  margin-top: 1rem;
  margin-left: 12rem;
}
</style>