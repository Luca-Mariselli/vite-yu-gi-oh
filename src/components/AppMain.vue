<script>
import store from '../Data/store.js'
import SingleCard from './SingleCard.vue';
export default {
    components: {
        SingleCard,
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
            <SingleCard v-for="(carta, i) in store.carte" :cartaSingola="carta" />
        </div>

    </main>




</template>

<style scoped></style>