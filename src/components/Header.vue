<template>
    <header class="container text-center">
        <h1>Workshop</h1>
        <div class="d-flex justify-content-between">
            <h2>Colors</h2>
            <div>
                <select name="" id="" v-model="selected">
                    <option value="">All</option>
                    <option value="fire">Fire</option>
                    <option value="summer">Summer</option>
                </select>
                <button class="btn btn-success" @click="getFilteredColors(selected)">Search</button>
            </div>
        </div>
    </header>
</template>

<script>
import { store } from '@/store';
export default {
    name: 'Header',
    data() {
        return {
            store,
            selected: ''
        }
    },
    methods: {
        getFilteredColors(parameter) {
            this.store.filteredArrayColors = this.store.colors.filter((element) => {
                return element.palette_name === parameter;
            })
            console.log(this.store.filteredArrayColors);
        }
    }
}
</script>

<style lang="scss" scoped></style>