<template>
    <section class="expert">
       <div class="container">
            <h2 class="expert__title">
                Мы изучаем и принимаем во внимание все мнения ведущих специалистов отрасли
            </h2>
            <div class="expert__block">

                    <div ref="prev" class="swiper-button-prev"></div>
                    <div ref="next" class="swiper-button-next"></div>


                <div class="expert__subtitle">
                    <p>Мнения специалистов</p>
                </div>
            </div>

            <Swiper
                class="expert__swiper"
                :modules="modules"
                :speed= "700"
                :navigation="{
                    prevEl: prev,
                    nextEl: next,
                }"
                :spaceBetween="44"
            >
                <Swiper-slide>Slide 1</Swiper-slide>
                <Swiper-slide>Slide 2</Swiper-slide>
                <Swiper-slide>Slide 3</Swiper-slide>
            </Swiper>
        </div>

    </section>
</template>

<script setup>
import { ref } from 'vue'
import { Swiper, SwiperSlide } from "swiper/vue"
import { Navigation } from 'swiper/modules'
import "swiper/css"
import 'swiper/css/navigation'



const modules = [Navigation]
const prev = ref(null)
const next = ref(null)

</script>

<style lang="scss" >
.expert {
    padding: 60px 0 120px;

    &__title {
        font-size: 40px;
        color: $black;
        font-weight: 500;
        line-height: 1.3;
        width: 70%;
    }

    &__subtitle {
        display: flex;
        justify-content: flex-end;

        p {
            font-size: 18px;
            font-weight: 500;
            color: $primary;
        }
    }

    &__swiper {
        margin-top: 40px;
        height: 700px;
    }

    &__block {
        margin-top: 44px;
        display: flex;
        align-items: center;
        justify-content: space-between;




    }

 

}


</style>