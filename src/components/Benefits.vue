<template>
   <section class="benefits">
        <div class="container">
                <div class="benefits__wrap">
                   <div
                        class="benefits__card"
                        v-for="card in cards"
                        :key="card.id"
                    >
                        <h3 class="benefits__card-title">{{ card.title }}</h3>
                        <div class="benefits__card-body">{{ card.desc }}</div>
                        <a href="#" class="benefits__card-footer">
                            <svg xmlns="http://www.w3.org/2000/svg" width="10" height="17" viewBox="0 0 10 17" fill="none">
                                <path d="M1 1L8.5 8.5L1 16" stroke="white" stroke-width="2"/>
                            </svg>
                        </a>
                   </div>
                </div>
        </div>
   </section>
</template>

<script setup>

const prop = defineProps({
    cards:{
        type:Array,
        required:true,
        default: () => []
    }
})

</script>

<style lang="scss" scoped>
.benefits {
    &__wrap {
        width: 100%;
        display: flex;
        align-items: center;
        justify-content: space-between;
        gap: 46px;
    }

    &__card {
        position: relative;
        display: flex;
        flex-direction: column;
        width: 25%;
        height: 413px;
        padding: 35px 35px 30px 35px;
        border-radius: 5px;
        background-color: $primary;
        background-image:linear-gradient(0deg, rgba(9, 46, 98, 0.30) 0%, rgba(65, 124, 209, 0.30) 100%);
        box-shadow: 0px 0px 10px 0px rgba(6, 31, 67, 0.30);
        transition: $transition;
        cursor: pointer;

        &:hover {
            transform: translateY(-3px);
            box-shadow: 0px 8px 8px 0px $blue;
        }

        &-title {
            color: #fff;
            line-height: 1.2;
            font-size: 24px;
        }

        &-body {
            margin-top: 15px;
            color: rgba($secondary, 0.5);
            line-height: 1.4;
            font-size: 14px;
        }

        &-footer {
            position: absolute;
            bottom: 40px;
            right: 30px;

            svg path {
                transition: $transition;
            }

            &:hover {
                svg path {
                    stroke: $gray;
                }
            }
        }
    }
}

@media (max-width: 1200px) {
    .benefits {
        &__wrap {
            gap: 25px;
        }

        &__card {
            padding: 25px;
        }
    }
}
@media (max-width: 992px) {
    .benefits {
        &__wrap {
            flex-wrap: wrap;
            gap: 46px;
        }

        &__card {
            width: calc(50% - 23px);
        }
    }
}
@media (max-width: 768px) {
    .benefits {
        &__wrap {
            gap: 30px;
        }

        &__card {
            width: calc(50% - 15px);
        }
    }
}
@media (max-width: 576px) {
    .benefits {
        &__wrap {
            flex-direction: column;
        }

        &__card {
            width: 100%;
            height: 300px;
        }
    }
}
@media (max-width: 375px) {
    .benefits {
        &__card {
            height: 270px;

            &-title {
                font-size: 18px;
            }

            &-body {
                font-size: 12px;
            }
        }

    }
}

</style>