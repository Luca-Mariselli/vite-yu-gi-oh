<script>
import store from '../Data/store.js'
export default {
    props: {
        cartaSingola: String
    },
    components: {

    },
    data() {
        return {
            store
        }
    },
    methods: {

    },
    mounted() {
    }
}
</script>

<template>
    <main>
        <div class="contenitore">
            <div class="carta" v-for="(cartaSingola, i) in store.carte">
                <img class="img-w" :src="this.store.carte[i].card_images[0].image_url" alt="">
                <div>{{ cartaSingola.name }}</div>
                <div>{{ cartaSingola.race }}</div>
            </div>
        </div>

    </main>
</template>

<style scoped>
.contenitore {
    background-color: white;
    width: 80%;
    height: 700px;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    margin: 0 auto;
    margin-top: 4rem;
    justify-content: space-between;
}

.carta {
    width: 20%;
    padding: 1rem;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-between;
}

.img-w {
    width: 60%;
    margin-bottom: 1rem;
}
</style>