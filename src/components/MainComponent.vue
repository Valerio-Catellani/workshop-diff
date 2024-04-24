<template>
    <main class="container">
        <div class="color-container">
            <ColorComponent v-for="(color, index) in store.filteredArrayColors" :key="index" :color="color"
                @click="changeColor(color)" role="button" />
        </div>
        <div class="box border border-black d-flex flex-column align-items-center justify-content-center gap-3 text-white"
            :style="`background-color: ${store.activeColor.hex}`">
            <h4>{{ store.activeColor.label }}</h4>
            <h6>{{ store.activeColor.hex }}</h6>
            <p>{{ store.activeColor.palette_name }}</p>
        </div>
    </main>
</template>

<script>
import { store } from '../store.js';
import ColorComponent from './ColorComponent.vue';
export default {
    name: "MainComponent",
    components: {
        ColorComponent
    },
    data() {
        return {
            store
        }
    },
    methods: {
        changeColor(element) {
            this.store.activeColor = element
        }
    },
    mounted() {
        this.changeColor(store.colors[0]);
        this.store.filteredArrayColors = store.colors;
    }
}
</script>

<style lang="scss" scoped>
.color-container {
    display: flex;
    justify-content: space-between;
    margin: 0 20px;
}

.box {
    height: 200px;
    width: 500px;
    margin: 50px auto;
}
</style>