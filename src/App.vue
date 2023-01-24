<script>
import axios from 'axios';
import { store } from './data/store';

import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppFooter from './components/AppFooter.vue';

export default {
    components: { AppHeader, AppMain, AppFooter },
    data() {
        return {
            store
        }
    },
    methods: {
        fetchCreatures(url) {
            axios.get(url)
                .then(res => {
                    store.creatures = res.data.docs
                })
        }
    },
    created() {
        this.fetchCreatures(store.apiUri)
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
