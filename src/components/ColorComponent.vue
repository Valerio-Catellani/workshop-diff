<template>
    <div class="my-circle" :style="`background-color: ${color.hex}`">

    </div>
</template>

<script>
import { store } from '../store.js'
export default {
    name: 'ColorComponent',
    props: {
        color: Object
    },
    data() {
        return {
            store
        }
    },
}
</script>

<style lang="scss" scoped>
/* @use '../assets/styles/partials/variables' as *; */

.my-circle {
    height: 50px;
    aspect-ratio: 1/1;
    border-radius: 50%;
    border: 1px solid rgb(0, 0, 0);
}
</style>