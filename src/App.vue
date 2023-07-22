<template>
    <Header />
    <main>
        <Info />
        <Desc />
        <Benefits :cards="cardInfo"/>
        <Slider :items="slideInfo"/>
        <Expert
            :items="slideExpertAuthor"
            title="Мы изучаем и принимаем во внимание все мнения ведущих специалистов отрасли"
            subtitle="Мнения специалистов"
        />
    </main>
    <Footer />
</template>

<script setup>
import { slideExpertAuthor, slideInfo, cardInfo } from "@/js/constants"
import Header from './layouts/header/Header.vue'
import Footer from './layouts/footer/Footer.vue'
import Expert from './components/Expert.vue'
import Slider from './components/Slider.vue'
import Benefits from "./components/Benefits.vue"
import Desc from "./components/Desc.vue"
import Info from "./components/Info.vue"

</script>
<style scoped>

</style>
