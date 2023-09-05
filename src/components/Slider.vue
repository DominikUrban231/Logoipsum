<template>
    <div class="wrapper">
        <button @click="prevSlide"><img src="./../assets/svg/arrow-left.svg" alt=""></button>
        <div class="carusel">
            <!-- <img src="./../assets/img/gallery-1.jpg" alt="">
            <img src="./../assets/img/gallery-2.jpg" alt="">
            <img src="./../assets/img/gallery-3.jpg" alt="">
            <img src="./../assets/img/gallery-4.jpg" alt=""> -->
        <!-- <img
            v-for="(slide, index) in slides"
            :key="index"
            :src="slide.image"
            :alt="slide.alt"
            :class="{ 'preloaded': slide.preload }"
        > -->
            <img src="currentImage" alt="">
        </div>
        <button @click="nextSlide"><img src="./../assets/svg/arrow-right.svg" alt=""></button>
        <div class="pagination">

        </div>
    </div>
</template>
<script>
export default {
data() {
    return {
        slides: [
            "./../assets/img/gallery-1.jpg",
            "./../assets/img/gallery-2.jpg",
            "./../assets/img/gallery-3.jpg",
            "./../assets/img/gallery-4.jpg",

            // { image: "./../assets/img/gallery-1.jpg", alt: "Slide 1" },
            // { image: "./../assets/img/gallery-2.jpg", alt: "Slide 2" },
            // { image: "./../assets/img/gallery-3.jpg", alt: "Slide 3" },
            // { image: "./../assets/img/gallery-4.jpg", alt: "Slide 3" },
        ],
        currentIndex: 0,
        };
},
methods: {
    prevImage() {
      if (this.currentImageIndex > 0) {
        this.currentImageIndex--;
      }
    },
    nextImage() {
      if (this.currentImageIndex < this.images.length - 1) {
        this.currentImageIndex++;
      }
    },
    goToSlide(index) {
    this.currentIndex = index;
    },
},
computed: {
    currentImage() {
      return this.images[this.currentImageIndex];
    },
  },
};
</script>

<style lang="scss">
.wrapper {
    max-width: 1200px;
    display: flex;
    align-content: center;
    .carusel {
    white-space: nowrap;
        img {
            height: 70vh;
            object-fit: cover;
            width: 70%;
        }
    }
}
</style>