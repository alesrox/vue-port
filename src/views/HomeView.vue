<template>
  <div class="home">
    <BannerFolio />
    <Carousel />
    <Skills />
    <Certificates />
    <Footer />
  </div>
</template>

<script>
import BannerFolio from '@/components/Banner.vue'
import Carousel from '@/components/Carousel.vue'
import Skills from '@/components/HardSkills.vue'
import Certificates from '@/components/Certificates.vue'
import Footer from '@/components/Footer.vue'


export default {
  name: 'HomeView',
  components: {
    BannerFolio, Carousel, Skills, Certificates, Footer
  }, 
}
</script>
