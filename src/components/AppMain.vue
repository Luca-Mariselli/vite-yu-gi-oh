<script>
import SingleCard from './SingleCard.vue';

export default {
    props: {
        filteredCards: {
            type: Array,
            default: () => [],
        },
    },
    components: {
        SingleCard,
    },
};
</script>

<template>
    <div class="contenitore">
        <div v-if="filteredCards.length > 0">
            <SingleCard v-for="(carta, i) in filteredCards" :key="i" :cartaSingola="carta" />
        </div>
        <div v-else>
            Nessuna carta corrispondente all'archetipo selezionato.
        </div>
    </div>
</template>

<style scoped></style>