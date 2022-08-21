<template>
  <section class="main__courses our-courses">
    <div class="our-courses__container _container">
      <h1 class="our-courses__title _title">
        O'zingiz uchun mos kursni tanlang
      </h1>
      <swiper
        :slides-per-view="4"
        :space-between="50"
        :loop="true"
        @swiper="onSwiper"
        @slideChange="onSlideChange"
        :breakpoints="{
          '300': {
            slidesPerView: 1,
            spaceBetween: 40,
          },
          '400': {
            slidesPerView: 1,
            spaceBetween: 20,
          },
          '640': {
            slidesPerView: 2,
            spaceBetween: 20,
          },
          '768': {
            slidesPerView: 3,
            spaceBetween: 40,
          },
          '991.98': {
            slidesPerView: 4,
            spaceBetween: 50,
          },
        }"
        :pagination="{
          clickable: true,
        }"
        :modules="modules"
      >
        <swiper-slide>
          <div class="our-courses__slider slider">
            <div class="slider__icon">
              <img src="../assets/images/icons/ingliz-tili.png" alt="Eng" />
            </div>
            <h2 class="slider__title">General English</h2>
            <ul class="slider__info-list">
              <li class="slider__info-list__item">
                <img src="../assets/images/icons/checked.png" alt="check" />
                Ingliz tilini noldan yoki ma’lum darajadan o’rganmoqchi
                bo'lganlar uchun
              </li>
              <li class="slider__info-list__item">
                <img src="../assets/images/icons/checked.png" alt="check" />
                Kurs davomiyligi: 5 ta bosqich, 1 ta bosqich - 3 oy
              </li>
              <li class="slider__info-list__item">
                <img src="../assets/images/icons/checked.png" alt="check" />
                Minimal bosqich: Noldan yoki undan yuqori
              </li>
            </ul>
          </div>
        </swiper-slide>
        <swiper-slide>
          <div class="our-courses__slider slider">
            <div class="slider__icon">
              <img
                src="../assets/images/icons/pazandachilik.png"
                alt="Kitchen"
              />
            </div>
            <h2 class="slider__title">Pazandachilik</h2>
            <ul class="slider__info-list">
              <li class="slider__info-list__item">
                <img src="../assets/images/icons/checked.png" alt="check" />
                Pazandachilik kurslarimizda barcha mahsulotlar markazimiz
                tomonidan taqdim qilinadi.
              </li>
              <li class="slider__info-list__item">
                <img src="../assets/images/icons/checked.png" alt="check" />
                Kurs davomiyligi: 1 oy
              </li>
              <li class="slider__info-list__item">
                <img src="../assets/images/icons/checked.png" alt="check" />
                Minimal bosqich: Noldan yoki undan yuqori
              </li>
            </ul>
          </div>
        </swiper-slide>
        <swiper-slide>
          <div class="our-courses__slider slider">
            <div class="slider__icon">
              <img src="../assets/images/icons/web.png" alt="Web" />
            </div>
            <h2 class="slider__title">Web dasturlash</h2>
            <ul class="slider__info-list">
              <li class="slider__info-list__item">
                <img src="../assets/images/icons/checked.png" alt="check" />
                Web dasturlash kursimiz amaliyotga moslashgan va siz portfolio
                bilan tamomlaysiz kursni.
              </li>
              <li class="slider__info-list__item">
                <img src="../assets/images/icons/checked.png" alt="check" />
                Kurs davomiyligi: 6 ta bosqich, 1 ta bosqich - 1 oy
              </li>
              <li class="slider__info-list__item">
                <img src="../assets/images/icons/checked.png" alt="check" />
                Minimal bosqich: Noldan yoki undan yuqori
              </li>
            </ul>
          </div>
        </swiper-slide>
        <swiper-slide>
          <div class="our-courses__slider slider">
            <div class="slider__icon">
              <img src="../assets/images/icons/arab-tili.png" alt="Eng" />
            </div>
            <h2 class="slider__title">Arab tili</h2>
            <ul class="slider__info-list">
              <li class="slider__info-list__item">
                <img src="../assets/images/icons/checked.png" alt="check" />
                Ingliz tilini noldan yoki ma’lum darajadan o’rganmoqchi
                bo'lganlar uchun
              </li>
              <li class="slider__info-list__item">
                <img src="../assets/images/icons/checked.png" alt="check" />
                Kurs davomiyligi: 5 ta bosqich, 1 ta bosqich - 3 oy
              </li>
              <li class="slider__info-list__item">
                <img src="../assets/images/icons/checked.png" alt="check" />
                Minimal bosqich: Noldan yoki undan yuqori
              </li>
            </ul>
          </div>
        </swiper-slide>
        <swiper-slide>
          <div class="our-courses__slider slider">
            <div class="slider__icon">
              <img
                src="../assets/images/icons/buxgalteriya.png"
                alt="buxgalter"
              />
            </div>
            <h2 class="slider__title">Buxgalteriya</h2>
            <ul class="slider__info-list">
              <li class="slider__info-list__item">
                <img src="../assets/images/icons/checked.png" alt="check" />
                Pazandachilik kurslarimizda barcha mahsulotlar markazimiz
                tomonidan taqdim qilinadi.
              </li>
              <li class="slider__info-list__item">
                <img src="../assets/images/icons/checked.png" alt="check" />
                Kurs davomiyligi: 1 oy
              </li>
              <li class="slider__info-list__item">
                <img src="../assets/images/icons/checked.png" alt="check" />
                Minimal bosqich: Noldan yoki undan yuqori
              </li>
            </ul>
          </div>
        </swiper-slide>
        <swiper-slide>
          <div class="our-courses__slider slider">
            <div class="slider__icon">
              <img src="../assets/images/icons/chevarchilik.png" alt="chevar" />
            </div>
            <h2 class="slider__title">Chevarchilik</h2>
            <ul class="slider__info-list">
              <li class="slider__info-list__item">
                <img src="../assets/images/icons/checked.png" alt="check" />
                Web dasturlash kursimiz amaliyotga moslashgan va siz portfolio
                bilan tamomlaysiz kursni.
              </li>
              <li class="slider__info-list__item">
                <img src="../assets/images/icons/checked.png" alt="check" />
                Kurs davomiyligi: 6 ta bosqich, 1 ta bosqich - 1 oy
              </li>
              <li class="slider__info-list__item">
                <img src="../assets/images/icons/checked.png" alt="check" />
                Minimal bosqich: Noldan yoki undan yuqori
              </li>
            </ul>
          </div>
        </swiper-slide>
      </swiper>
      <div class="slider__btn _btn">Kursga yozilish</div>
    </div>
  </section>
</template>

<script>
import { Swiper, SwiperSlide } from "swiper/vue";
import { Pagination } from "swiper";

import "swiper/css";
import "swiper/css/pagination";


export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    const onSwiper = (swiper) => {
      console.log(swiper);
    };
    const onSlideChange = () => {
      console.log("slide change");
    };
    return {
      onSwiper,
      onSlideChange,
      modules: [Pagination],
    };
  },
};
</script>
