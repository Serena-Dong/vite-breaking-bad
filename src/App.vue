<script>
import axios from 'axios';
import { store } from './data/store';
import { storetwo } from './data/store';

import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';

export default {
    components: { AppHeader, AppMain },
    data() {
        return {
            store,
            storetwo
        }
    },
    methods: {
        fetchCreatures(url = apiUri) {
            axios.get(url)
                .then(res => {
                    store.creatures = res.data.docs
                })
        },
        fetchTypes(url) {
            axios.get(url)
                .then(res => {
                    storetwo.types = res.data
                })
        },
        filterCreatures(type) {
            const url = type ? `https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons?eq[type1]=${type}` : store.apiUri;
            this.fetchCreatures(url)
        }
    },
    created() {
        this.fetchCreatures(store.apiUri)
        this.fetchTypes(storetwo.apiUri)
    }
}
</script>

<template>
    <AppHeader @filter-change="filterCreatures"></AppHeader>
    <AppMain></AppMain>
</template>

<style scoped>

</style>
