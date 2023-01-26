<script>
import { storetwo } from '../../data/store';

export default {
    data() {
        return {
            storetwo,
            selectedOption: ''
        }
    }
}
</script>

<template>
    <div>
        <select v-model="selectedOption" @change="$emit('option-change', selectedOption)">
            <option value=""> Select a ... </option>
            <option v-for="option in storetwo.types" :key="option" :value="option">{{ option }}</option>
        </select>
    </div>
</template>

<style lang="scss" scoped>
div {
    display: flex;
    justify-content: center;
    align-items: center;
}

select {
    width: 15rem;
    height: 2rem;

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