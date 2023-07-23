<template>
    <section class="slider">
        <div class="container">
            <div class="slider__buttons">
                <div ref="prev" class="swiper-button-prev"></div>
                <div ref="next" class="swiper-button-next"></div>
            </div>

            <Swiper
                class="slider__swiper"
                :modules="modules"
                :speed= "1200"
                :navigation="{
                    prevEl: prev,
                    nextEl: next,
                }"
                :slidesPerView="1"
                :spaceBetween="44"
                :effect="'creative'"
                :grabCursor="false"
                :breakpoints="breakpoints"
            >
                <Swiper-slide
                    v-for="item in items"
                    :key="item.id"
                >
                   <div class="slider__slide">
                        <div class="slider__slide-img">
                            <img :src="item.src" :alt="item.alt" />
                        </div>
                        <div class="slider__slide-info">
                            <p class="slider__slide-text">{{ item.desc }}</p>
                            <div class="slider__slide-date">{{ item.date }}</div>
                            <a href="#" class="slider__slide-link">
                               {{ item.link }}
                                <svg xmlns="http://www.w3.org/2000/svg" width="8" height="12" viewBox="0 0 8 12" fill="none">
                                    <path d="M1 1L6 6L1 11" stroke="#FDFDFD" stroke-width="2"/>
                                </svg>
                            </a>
                        </div>
                   </div>
                </Swiper-slide>

            </Swiper>
        </div>
    </section>
</template>

<script setup>
import { ref } from 'vue'
import { Swiper, SwiperSlide } from "swiper/vue"
import { Navigation, EffectCreative } from 'swiper/modules'
import "swiper/css"
import 'swiper/css/navigation'
import 'swiper/css/effect-creative'

const prop = defineProps({
    items:{
        type:Array,
        required:true,
        default: () => []
    }
})

const modules = [Navigation, EffectCreative]
const prev = ref(null)
const next = ref(null)

const breakpoints = {
    320: {
        slidesPerView: 1,
        spaceBetween: 25
    },
    992: {
        grabCursor:"true",
        creativeEffect:{
            prev: {
                shadow: true,
                translate: ['-120%', 0, -600],
            },
            next: {
                shadow: true,
                translate: ['120%', 0, -600],
            },
        }
    }
}

</script>

<style lang="scss" scoped>

.slider {
    &__buttons {
        position: relative;
        width: 100%;
        height: 23px;
    }

    .swiper-button-prev {
            left: 0;
        }
        .swiper-button-next {
            left: 50px;
        }

        .swiper-button-prev:after, .swiper-button-next:after {
            font-size: 22px;
        }

    &__swiper {
        margin-top: 35px;
    }

    &__slide {
        display: flex;
        height: 550px;

        &-img {
            max-width: 880px;
            width: 100%;

            img {
                width: 100%;
                height: 100%;
                object-fit: cover;
                border-radius: 5px 0px 0px 5px;
            }
        }

        &-info {
            width: 460px;
            display: flex;
            flex-direction: column;
            padding: 25px 40px 25px;
            border-radius: 0 5px 5px 0px;
            background-color: $primary;
            background-image: linear-gradient(0deg, rgba(9, 46, 98, 0.30) 0%, rgba(65, 124, 209, 0.30) 100%);
        }

        &-text {
            color: $secondary;
            font-size: 24px;
            line-height: 1.4;
        }

        &-date {
            margin-top: 20px;
            color: $slideBody;
        }

        &-link {
            display: flex;
            align-items: center;
            width: 100%;
            margin-top: 40px;
            color: $secondary;
            font-size: 18px;
            font-weight: 500;
            text-decoration: none;
            transition: $transition;

            &:hover {
                color: $gray;

                svg {
                    cursor: pointer;

                    path {
                        transition: $transition;
                        stroke: $gray;
                        }
                }
            }

            svg {
                margin-left: 4px;
            }

        }


    }
}


@media (min-width: 1300px) {
    .slider {
        &__slide {
            &-info {
                padding: 45px 80px 45px;
            }
        }
    }
}

@media (max-width: 992px) {
    .slider {
        &__slide {
            height: 450px;

            &-text {
                font-size: 20px;
            }
        }
    }
}
@media (max-width: 768px) {
    .slider {
        &__slide {
            height: 400px;

            &-info {
                padding: 15px;
            }

            &-link {
               margin-top: 20px;
            }
        }
    }
}
@media (max-width: 576px) {
    .slider {
        &__slide {
            position: relative;
            flex-direction: column;
            min-height: 400px;

            &-img {
                img {
                    border-radius: 5px 5px 0px 0px;
                }
            }

            &-info {
                position: absolute;
                bottom: 10px;
                width: 100%;
                border-radius: 0 0px 5px 5px;
            }

            &-text, &-link {
                font-size: 16px;
            }
        }

    }
}
@media (max-width: 425px) {
    .slider {
        &__slide {
            min-height: 420px;

            &-img {
                img {
                    min-height: 300px;
                }
            }

            &-text, &-link, &-date {
                font-size: 14px;
            }
        }

    }
}
</style>