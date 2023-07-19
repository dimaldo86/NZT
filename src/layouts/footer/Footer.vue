<template>
    <footer class="footer">
        <div class="container">
            <div class="row">
                <div class="col-lg-2 mb-2 mb-lg-0">
                    <div class="footer__info">
                        <div class="footer__text">Путь к богатству и могуществу</div>
                        <p class="footer__copyright">© «NZT-48», 2022</p>
                    </div>
                </div>
                <div class="col-lg-4 mb-2  mb-lg-0">
                    <div class="footer__data"><div>Согласие на обработку персональных данных</div></div>
                </div>
                <div class="col-lg-3 mb-2  mb-lg-0">
                    <div class="footer__confidentiality"><div>Политика конфиденциальности</div></div>
                </div>
                <div class="col-lg-3">
                    <div class="footer__author"><div class="footer__author_test">Тестовое задание от Country</div></div>
                </div>
            </div>
        </div>
    </footer>
</template>

<script setup>

</script>

<style lang="scss" scoped>
.footer {
    margin-top: auto;
    background-color: $darkBlue;
    padding: 47px 0 44px;
    color: $lightGray;

    &__text {
        color: $secondary;
        font-size: 24px;
        line-height: 1.2;
    }

    &__copyright {
        margin-top: 50px;
        margin-bottom: 0;
    }

    &__data, &__confidentiality, &__author {
        display: flex;
        flex-direction: column;
    }

    div {
        margin-top: auto;
    }

    &__author_test {
        align-self: flex-end;
    }
}

@media (max-width:1200px) {
    .footer {
       font-size: 14px;
    }
}
@media (max-width:992px) {
    .footer {
        &__copyright {
            margin-top: 30px;
        }

        &__author_test {
            align-self: flex-start;
        }
    }
}
@media (max-width:576px) {
    .footer {
        padding: 27px 0 24px;
        font-size: 12px;

        &__text {
            font-size: 18px;
        }
    }
}
</style>