<script>
export default {
    name: 'AppContents',
    props: {
        creature: Object
    }
}
</script>

<template>

    <a href="">
        <div class="card">
            <div class="img-box">
                <img :src=creature.imageUrl :alt=creature.name>
            </div>
            <div class="text">
                <p>#{{ creature.serial }}</p>
                <h2>{{ creature.name }}</h2>
                <p><em>{{ creature.type1 }}</em></p>
            </div>

        </div>
    </a>

</template>

<style lang="scss" scoped>
a {
    color: black;


    &:hover {
        color: rgb(0, 126, 0)
    }
}

.card {
    width: 220px;
    height: 350px;
    padding: 1rem 0 1rem;

    margin-bottom: 2rem;
    background-color: rgb(255, 255, 255);



    .img-box {
        display: flex;
        justify-content: center;

        img {
            border-radius: 10rem;
            object-fit: cover;
            width: 180px;
            height: 180px;

            &:hover {
                border: grey 2px solid;
            }
        }
    }

    .text {
        margin-left: 1rem;

        p {
            margin: 1rem 0 1rem
        }
    }

}
</style>