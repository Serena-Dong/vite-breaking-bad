<script>
export default {
    name: 'AppContents',
    props: {
        content: Object
    }
}
</script>

<template>

    <div class="card">
        <a href="">
            <img :src="content.thumb" :alt="content.type">

            <p>{{ content.series }}</p>
        </a>
    </div>

</template>

<style lang="scss" scoped>
@use '../../assets/scss/partials/variables' as *;

a {
    color: white;

    &:hover {
        color: $dc_blue;
    }
}

.card {
    width: 180px;
    height: 270px;

    img {
        object-fit: cover;
        width: 180px;
        height: 180px;

        &:hover {
            border: $dc_blue 2px solid;
        }
    }

    p {
        margin: 1rem 0 1rem
    }
}
</style>