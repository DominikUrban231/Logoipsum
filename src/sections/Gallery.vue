<template>
    <section id="gallery" class="gallery">
        <h1 class="red">GALERIA</h1>
        <Slider />
    </section>
</template>

<script>
import Slider from '@/components/Slider.vue';

export default {
    components: { Slider }
}
</script>

<style lang="scss">
.red {
    display: block;
    max-width: fit-content;
    border-bottom: 2px solid #FF4359;
    margin: auto;
    padding: 15px;
}
</style>