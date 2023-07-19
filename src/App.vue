<template>
    <Header />
    <main>
        <Slide
            :items="slideExpertAuthor"
            title="Мы изучаем и принимаем во внимание все мнения ведущих специалистов отрасли"
            subtitle="Мнения специалистов"
            slidesPerView="1.5"
        />
    </main>
    <Footer />
</template>

<script setup>
import { slideExpertAuthor } from "@/js/constants"
import Header from './layouts/header/Header.vue'
import Footer from './layouts/footer/Footer.vue'
import Slide from './components/Slide.vue'


</script>
<style scoped>

</style>
