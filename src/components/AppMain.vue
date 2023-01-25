<script>
import CreaturesCard from './contents/CreaturesCard.vue';
import { store } from '../data/store';

export default {
    components: { CreaturesCard },
    data() {
        return {
            store
        }
    }
}
</script>

<template>
    <main>

        <div class="contents">
            <div class="container">
                <div class="row">

                    <CreaturesCard v-for="creature in store.creatures" :key="creature.name" :creature="creature">
                    </CreaturesCard>

                </div>
            </div>
        </div>
    </main>
</template>

<style scoped>
.contents {
    background-color: rgb(26, 26, 26);
    min-height: 150px;
    padding: 3rem;

    display: flex;
    align-items: center;
}

.row {
    display: flex;
    flex-wrap: wrap;
    gap: 2%;

}
</style>
