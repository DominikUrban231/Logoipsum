<template>
    <div class="slider">
        <div class="slides" :style="{ transform: `translateX(${currentIndex * -100}%)` }">
            <div v-for="(slide, index) in slides" :key="index" class="slide">
                <img :src="slide.imageSrc" alt="Slide" />
            </div>
        </div>

        <button @click="prevSlide" class="prev">Poprzedni</button>
        <button @click="nextSlide" class="next">Następny</button>

        <div class="pagination">
        <span
            v-for="(slide, index) in slides"
            :key="index"
            @click="goToSlide(index)"
            :class="{ active: index === currentIndex }"
        ></span>
    </div>
  </div>
</template>
<script>
export default {
    data() {
        return {
            currentIndex: 0,
            sliders: [
            { imageSrc: './../assets/img/gallery-1.jpg' },
            { imageSrc: './../assets/img/gallery-2.jpg' },
            { imageSrc: './../assets/img/gallery-3.jpg' },
            { imageSrc: './../assets/img/gallery-4.jpg' },
            ]
            
        }
    }
}
</script>