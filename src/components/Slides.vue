<template>
  <div id="slides">
      <vueper-slides
        :touchable="false"
        :arrows="false"
        :bullets="false"
        fade
        :autoplay="true"
        fixed-height="400px"
      >
        <vueper-slide 
            v-for="(slide, i) in slides" 
            :key="i" 
            :image="slide.image"
            :duration="slide.duration" />
      </vueper-slides>
  </div>
</template>

<script>
    import { VueperSlides, VueperSlide } from 'vueperslides'
    import 'vueperslides/dist/vueperslides.css'

    export default {
        components: { VueperSlides, VueperSlide },
        data: () => ({
            slides: [
                {
                    image: require('@/assets/image1.jpg'),
                    duration: 5000
                },
                {
                    image: require('@/assets/image2.jpg'),
                    duration: 1000
                },
                {
                    image: require('@/assets/image3.jpg'),
                    duration: 5000
                }
            ]
        })
    }
</script>

<style>
    .thumbnails {
        margin: auto;
        max-width: 300px;
    }

    .thumbnails .vueperslide {
        box-sizing: border-box;
        border: 1px solid #fff;
        transition: 0.3s ease-in-out;
        opacity: 0.7;
        cursor: pointer;
    }

    .thumbnails .vueperslide--active {
        box-shadow: 0 0 6px rgba(0, 0, 0, 0.3);
        opacity: 1;
        border-color: #000;
    }
</style>
