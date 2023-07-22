<template>
    <section class="expert">
       <div class="container">
            <h2 class="expert__title">{{ title }}</h2>
            <div class="expert__block">
                <div ref="prev" class="swiper-button-prev"></div>
                <div ref="next" class="swiper-button-next"></div>
                <div class="expert__subtitle">{{ subtitle }}</div>
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
                :breakpoints="breakpoints"
            >
                <Swiper-slide
                    class="expert__slide"
                    v-for="item in items"
                    :key="item.id"
                >
                    <div class="expert__slide-title">
                        <div class="expert__slide-wrap">
                            <div class="expert__slide-name">{{ item.name }}</div>
                            <p class="expert__slide-subtitle">{{ item.job }}</p>
                        </div>
                        <div class="expert__slide-img">
                            <img :src="item.src" :alt="item.name">
                        </div>
                    </div>
                    <p class="expert__slide-body">{{ item.quote }}</p>
                    <a href="#" class="expert__slide-footer">
                        <span>Смотреть видео</span>
                        <svg xmlns="http://www.w3.org/2000/svg" width="8" height="12" viewBox="0 0 8 12" fill="none">
                            <path d="M1 1L6 6L1 11" stroke="white" stroke-width="2"/>
                        </svg>
                    </a>
                </Swiper-slide>
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

const props = defineProps({
    title:{
        type:String,
        required:false
    },
    subtitle: {
        type:String,
        required:false
    },
    items:{
        type:Array,
        required:true,
        default: () => []
    }
})

const modules = [Navigation]
const prev = ref(null)
const next = ref(null)

const breakpoints = {
    320: {
        slidesPerView: 1,
        spaceBetween: 25
    },
    992: {
        slidesPerView: 1.5,
        spaceBetween: 44
    }
}

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
        font-size: 18px;
        font-weight: 500;
        color: $primary;
    }

    &__swiper {
        margin-top: 42px;
    }

    .swiper-slide {
        padding: 61px 97px 64px 110px;
        border-radius: 5px;
        background: linear-gradient(0deg, rgba(0, 0, 0, 0.20) 0%, rgba(0, 0, 0, 0.20) 100%), linear-gradient(0deg, rgba(9, 46, 98, 0.30) 0%, rgba(65, 124, 209, 0.30) 100%), $primary;
        box-shadow: 0px 0px 10px 0px rgba(6, 31, 67, 0.30);

        &-active {
            background-color: $primary;
            background-image:  linear-gradient(0deg, rgba(9, 46, 98, 0.30) 0%, rgba(65, 124, 209, 0.30) 100%);
        }
    }

    &__block {
        position: relative;
        display: flex;
        align-items: center;
        justify-content: end;
        margin-top: 44px;

        .swiper-button-prev {
            left: 0;
        }
        .swiper-button-next {
            left: 50px;
        }

        .swiper-button-prev:after, .swiper-button-next:after {
            font-size: 22px;
        }
    }

    &__slide {
        display: flex;
        flex-direction: column;

        &-title {
            display: flex;
            justify-content: space-between;
            width:100% ;
        }

        &-wrap {
            display: flex;
            flex-direction: column;
            width: 70%;
        }

        &-name {
            color: #FFF;
            font-size: 24px;
            letter-spacing: 0.72px;
            text-transform: uppercase;
        }

        &-subtitle {
            color: $slideSubtitle;
            margin-top: 20px;
            font-size: 14px;
        }

        &-body {
            margin-top: 76px;
            color: $slideBody;
            font-size: 30px;
            line-height:1.4;
        }
        &-footer {
            margin-top: 40px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            text-decoration: none;
            transition: $transition;

            &:hover {
                span {
                    color: $gray;
                }


                    svg {
                        cursor: pointer;

                        path {
                            transition: $transition;
                            stroke: $gray;
                            }
                    }
                }

            span {
                color: #FFF;
                font-size: 18px;
                font-weight: 500;
                cursor: pointer;
                transition: $transition;
            }

            svg {
                cursor: pointer;
            }
        }
    }



}

@media (max-width: 992px) {
    .expert {
        padding: 50px 0 90px;

        &__title {
            width: 100%;
        }

        .swiper-slide {
            padding: 50px 80px;
        }
    }
}

@media (max-width: 768px) {
    .expert {
        padding: 40px 0 70px;

        &__title {
           font-size: 36px;
        }

        .swiper-slide {
            padding: 30px 60px;
        }

        &__slide {
            &-body {
                margin-top: 56px;
            }
        }
    }
}

@media (max-width: 576px) {
    .expert {
        padding: 30px 0 60px;

        &__title {
           font-size: 28px;
        }

        &__block {
            margin-top: 24px;

            .swiper-button-prev:after, .swiper-button-next:after {
                font-size: 18px;
            }
        }

        &__swiper {
            margin-top: 32px;
        }

        .swiper-slide {
            padding: 20px 40px ;
        }

        &__slide {
            &-name {
                font-size: 18px;
            }

            &-body {
                margin-top: 30px;
                font-size: 20px;
            }

            &-footer {
                margin-top: 20px;
            }
        }
    }
}

@media (max-width: 375px) {
    .expert {

        padding: 20px 0 40px;

        &__title {
           font-size: 24px;
        }

        &__subtitle {
            font-size: 14px;
        }

        &__block {
            .swiper-button-prev:after, .swiper-button-next:after {
                font-size: 14px;
            }
        }

        &__swiper {
            margin-top: 22px;
        }

        .swiper-slide {
            padding: 10px 20px;
        }

        &__slide {
            &-name {
                font-size: 16px;
            }

            &-subtitle {
                font-size: 11px;
            }

            &-body {
                font-size: 16px;
            }

            &-footer {

                span {
                    font-size: 14px;
                }
            }
        }
    }
}

</style>