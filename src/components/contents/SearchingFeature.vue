<script>
import { storetwo } from '../../data/store';

export default {
    data() {
        return {
            storetwo
        }
    }
}
</script>

<template>
    <form action="">
        <select name="" id="">
            <option v-for="(kind, i ) in storetwo.types" value="">{{ kind }}</option>
        </select>
        <button type="submit">Cerca</button>
    </form>
</template>

<style>
form {
    display: flex;
    justify-content: center;
    align-items: center;
}

select {
    width: 15rem;
    height: 2rem;
    padding: 1rem;
    border-radius: 10px;
    margin-right: 5px;

}

button {
    width: 4rem;
    height: 2.2rem;
    border-radius: 10px;
    cursor: pointer;
}
</style>