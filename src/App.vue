<script>
import axios from 'axios';
import { store } from './data/store';
import { storetwo } from './data/store';

import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppFooter from './components/AppFooter.vue';

export default {
    components: { AppHeader, AppMain, AppFooter },
    data() {
        return {
            store,
            storetwo
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
    <AppMain></AppMain>
    <AppFooter></AppFooter>
</template>

<style scoped>

</style>
