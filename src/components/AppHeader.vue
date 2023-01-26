<script>
import selectedOption from '../components/contents/selectedOption.vue';

export default {
    components: { selectedOption },
    emits: ['filter-change']
}

</script>

<template>
    <header>
        <div class="container">
            <div class="logo">
                <img src="../assets/img/International_Pokémon_logo.svg.png" alt="">
            </div>
        </div>
        <div class="filter">
            <selectedOption @option-change="$emit('filter-change', $event)"></selectedOption>
        </div>
    </header>
</template>

<style scoped>
.container {
    display: flex;
    justify-content: center;
}

.logo {
    width: 400px;
    margin: 1rem;
}
</style>
