<template>
   <section class="info">
        <div class="container">
            <div class="info__wrap">
                <div class="info__items">
                    <a href="#" class="info__item">
                        <h3 class="info__item-title">История</h3>
                        <div  class="info__item-link">
                            <svg xmlns="http://www.w3.org/2000/svg" width="9" height="14" viewBox="0 0 9 14" fill="none">
                                <path d="M1 1L7 7L1 13" stroke="#1E5AAF" stroke-width="2"/>
                            </svg>
                        </div>
                    </a>
                    <a href="#" class="info__item">
                        <h3 class="info__item-title">Состав препарата</h3>
                        <div  class="info__item-link">
                            <svg xmlns="http://www.w3.org/2000/svg" width="9" height="14" viewBox="0 0 9 14" fill="none">
                                <path d="M1 1L7 7L1 13" stroke="#1E5AAF" stroke-width="2"/>
                            </svg>
                        </div>
                    </a>
                </div>
                <div class="info__items">
                    <a href="#" class="info__item">
                        <h3 class="info__item-title">Технология производства</h3>
                        <div  class="info__item-link">
                            <svg xmlns="http://www.w3.org/2000/svg" width="9" height="14" viewBox="0 0 9 14" fill="none">
                                <path d="M1 1L7 7L1 13" stroke="#1E5AAF" stroke-width="2"/>
                            </svg>
                        </div>
                    </a>
                    <a href="#" class="info__item">
                        <h3 class="info__item-title">Механизм действия</h3>
                        <div  class="info__item-link">
                            <svg xmlns="http://www.w3.org/2000/svg" width="9" height="14" viewBox="0 0 9 14" fill="none">
                                <path d="M1 1L7 7L1 13" stroke="#1E5AAF" stroke-width="2"/>
                            </svg>
                        </div>
                    </a>
                </div>
                <div class="info__items">
                    <a href="#" class="info__item">
                        <h3 class="info__item-title">Инструкция</h3>
                        <div  class="info__item-link">
                            <svg xmlns="http://www.w3.org/2000/svg" width="9" height="14" viewBox="0 0 9 14" fill="none">
                                <path d="M1 1L7 7L1 13" stroke="#1E5AAF" stroke-width="2"/>
                            </svg>
                        </div>
                    </a>
                    <a href="#" class="info__item">
                        <h3 class="info__item-title">Рег. удостоверение</h3>
                        <div  class="info__item-link">
                            <svg xmlns="http://www.w3.org/2000/svg" width="9" height="14" viewBox="0 0 9 14" fill="none">
                                <path d="M1 1L7 7L1 13" stroke="#1E5AAF" stroke-width="2"/>
                            </svg>
                        </div>
                    </a>
                </div>

            </div>
        </div>
   </section>
</template>

<script setup>

</script>

<style lang="scss" scoped>
.info {
    padding-top: 50px;

    &__wrap {
        width: 100%;
        display: flex;
        justify-content: space-between;
        column-gap: 45px;
    }

    &__items {
        width: calc(33.3% - 22.5px);
    }
    &__item {
        position: relative;
        display: flex;
        align-items: center;
        justify-content: space-between;
        padding: 25px 0;
        padding-right: 8px;
        text-decoration: none;

        &:hover {
            .info__item-title {
                transform: translateX(5px);
            }

            svg {
                transform: translateX(-5px);
            }
        }

        &::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            height: 1px;
            width: 100%;
            background-color: $infoBefore;
        }

        &-title {
            color: $black;
            font-size: 18px;
            line-height: normal;
            transition: $transition;
        }

        svg {
            transition: $transition;
        }
    }
}

@media (max-width: 1200px) {
    .info {

        &__wrap {
            column-gap: 25px;
        }

        &__items {
            width: calc(33.3% - 12.5px);
        }
    }
}

@media (max-width: 992px) {
    .info {
        &__item {
           &-title {
            font-size: 16px;
           }
        }
    }
}
@media (max-width: 768px) {
    .info {
        &__wrap {
            flex-wrap: wrap;
        }

        &__items {
                width: 100%;
        }
    }
}
@media (max-width: 375px) {
    .info {
        &__item {
                &-title {
                    font-size: 14px;
                }
        }
    }
}
</style>