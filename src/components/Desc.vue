<template>
    <section class="desc">
        <div class="container">
            <div class="row">
                <div class="col-lg-6 col-md-8">
                    <h2 class="desc__title">Препарат NZT-48</h2>
                    <div class="desc__info">
                        <p>
                            Действует на клеточном уровне,
                            улучшая метаболизм клеток и восстанавливая их нормальные функции.
                        </p>
                        <p>
                            Благодаря этому достигается широчайший спектр медицинских показаний и
                            становится возможным применение в самых разных областях медицины.
                        </p>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>

</script>

<style lang="scss" scoped>
.desc {
    &__title {
        color: $primary;
        font-size: 40px;
        font-weight: 500;
        line-height: 1.3;
    }

    &__info {
        margin-top: 40px;
        color: $gray;
        font-size: 24px;
        line-height: 1.4;

        p {
            margin-bottom: 30px;

            &:last-child {
                margin-bottom: 0;
            }
        }
    }
}
@media (max-width: 576px) {
    .desc {
        &__title {
            font-size: 24px;
        }

        &__info {
            margin-top: 20px;
            font-size: 16px;

            p {
                margin-bottom: 15px;
            }
        }
    }
}
</style>