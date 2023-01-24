<script>
import AppContents from './contents/AppContents.vue'
export default {
    components: { AppContents }
}
</script>

<template>
    <main>
        <div class="contents">
            <div class="container">
                <div class="row">

                    <AppContents v-for="content in contents" :key="content.series" :content="content"></AppContents>

                </div>
            </div>
        </div>
    </main>
</template>

<style scoped>
.contents {
    background-color: rgb(154, 154, 154);
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
