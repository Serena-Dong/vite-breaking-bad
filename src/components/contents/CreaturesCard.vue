<script>
export default {
    name: 'AppContents',
    props: {
        creature: Object
    }
}
</script>

<template>

    <div class="card">
        <a href="">
            <img :src=creature.imageUrl alt="">
            <p></p>
            <h2></h2>
            <p><em></em></p>

        </a>
    </div>

</template>

<style lang="scss" scoped>
a {
    color: white;

    &:hover {
        color: grey;
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
            border: grey 2px solid;
        }
    }

    p {
        margin: 1rem 0 1rem
    }
}
</style>