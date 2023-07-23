<template>
   <section class="banner">
        <div class="container">
            <div class="row">
               <div class="col-xl-6 col-lg-8">
                  <h1 class="banner__title">Путь к богатству и могуществу</h1>
                  <a href="#" class="banner__link">
                     О препарате
                     <svg xmlns="http://www.w3.org/2000/svg" width="8" height="12" viewBox="0 0 8 12" fill="none">
                        <path d="M1 1L6 6L1 11" stroke="white" stroke-width="2"/>
                     </svg>
                  </a>
               </div>
            </div>
        </div>
   </section>
</template>

<script setup>

</script>

<style lang="scss" scoped>
.banner {
    background: url('src/img/banner/banner.png') no-repeat center / cover;
    min-height: 450px;
    max-width: 1440px;
    width: 100%;
    margin:  0 auto;
    padding: 130px 0 84px;

    &__title {
      color: #FFF;
      font-size: 80px;
      font-weight: 500;
      line-height: 1.1;
   }

   &__link {
      display: inline-block;
      text-decoration: none;
      margin: 40px auto;
      color: #FFF;
      font-size: 18px;
      font-weight: 500;
      line-height: normal;
      margin-bottom: 0;
      transition: $transition;

      &:hover {
         color: $primary;

         svg {
            path {
               stroke:$primary;
            }
         }
      }

      svg {
         margin-left: 15px;

         path {
            transition: $transition;
         }
      }
   }
}
@media (max-width: 992px) {
    .banner {
      padding: 100px 0 64px;
      min-height: auto;

        &__title {
         font-size: 64px;
        }
    }
}
@media (max-width: 768px) {
    .banner {
        &__title {
         font-size: 56px;
        }
    }
}
@media (max-width: 576px) {
    .banner {
      padding: 80px  0 64px;

        &__title {
         font-size: 36px;
        }
    }
}
@media (max-width: 576px) {
    .banner {
      padding: 80px  0 34px;

        &__title {
         font-size: 28px;
        }

        &__link {
            font-size: 16px;
        }
    }
}
</style>