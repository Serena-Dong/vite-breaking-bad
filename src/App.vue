<script>
import axios from 'axios';
import { store } from './data/store';
import { storetwo } from './data/store';

import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import SearchingFeature from './components/contents/SearchingFeature.vue';

export default {
    components: { AppHeader, AppMain, SearchingFeature },
    data() {
        return {
            store,
            storetwo,
            searchType: ''
        }
    },
    computed: {
        typeFilter() {
            return store.creatures.filter(creature => {
                creature.include(this.searchType)
                return creature
            })
        }
    },
    methods: {
        fetchCreatures(url) {
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
        }
    },
    created() {
        this.fetchCreatures(store.apiUri)
        this.fetchTypes(storetwo.apiUri)
    }
}
</script>

<template>
    <AppHeader></AppHeader>
    <div class="searching-bar">
        <SearchingFeature>
        </SearchingFeature>
    </div>
    <AppMain></AppMain>
</template>

<style scoped>

</style>
