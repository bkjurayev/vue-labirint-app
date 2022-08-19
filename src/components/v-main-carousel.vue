<template>
  <div class="_container">
    <div class="main__courses our-courses-slider">
      <h1 class="our-courses__title _title">O'zingiz uchun mos kursni tanlang</h1>
      <swiper
        :slides-per-view="4"
        :space-between="50"
        @swiper="onSwiper"
        @slideChange="onSlideChange"
      >
        <swiper-slide>
          <div class="our-courses-slider__body">
            <div class="our-courses-slider__icon">
              <img src="../assets/images/icons/eng.png" alt="Eng" />
            </div>
            <h2 class="our-courses-slider__title">General English</h2>
            <ul class="our-courses-slider__info-list">
              <li class="our-courses-slider__info-list__item">
                Ingliz tilini noldan yoki ma’lum darajadan o’rganmoqchi bo'lganlar
                uchun
              </li>
              <li class="our-courses-slider__info-list__item">
                Kurs davomiyligi: 5 ta bosqich, 1 ta bosqich - 3 oy
              </li>
              <li class="our-courses-slider__info-list__item">
                Minimal bosqich: Noldan yoki undan yuqori
              </li>
            </ul>
          </div>
        </swiper-slide>
        <swiper-slide>
          <div class="our-courses-slider__body">
            <div class="our-courses-slider__icon">
              <img src="../assets/images/icons/kitchen.svg" alt="Kitchen" />
            </div>
            <h2 class="our-courses-slider__title">Pazandachilik</h2>
            <ul class="our-courses-slider__info-list">
              <li class="our-courses-slider__info-list__item">
                Pazandachilik kurslarimizda barcha mahsulotlar markazimiz
                tomonidan taqdim qilinadi.
              </li>
              <li class="our-courses-slider__info-list__item">
                Kurs davomiyligi: 1 oy
              </li>
              <li class="our-courses-slider__info-list__item">
                Minimal bosqich: Noldan yoki undan yuqori
              </li>
            </ul>
          </div>
        </swiper-slide>
        <swiper-slide>
          <div class="our-courses-slider__body">
            <div class="our-courses-slider__icon">
              <img src="../assets/images/icons/web.svg" alt="Web" />
            </div>
            <h2 class="our-courses-slider__title">Web dasturlash</h2>
            <ul class="our-courses-slider__info-list">
              <li class="our-courses-slider__info-list__item">
                Web dasturlash kursimiz amaliyotga moslashgan va siz portfolio
                bilan tamomlaysiz kursni.
              </li>
              <li class="our-courses-slider__info-list__item">
                Kurs davomiyligi: 6 ta bosqich, 1 ta bosqich - 1 oy
              </li>
              <li class="our-courses-slider__info-list__item">
                Minimal bosqich: Noldan yoki undan yuqori
              </li>
            </ul>
          </div>
        </swiper-slide>
        <swiper-slide>
          <div class="our-courses-slider__body">
            <div class="our-courses-slider__icon">
              <img src="../assets/images/icons/eng.png" alt="Eng" />
            </div>
            <h2 class="our-courses-slider__title">General English</h2>
            <ul class="our-courses-slider__info-list">
              <li class="our-courses-slider__info-list__item">
                Ingliz tilini noldan yoki ma’lum darajadan o’rganmoqchi bo'lganlar
                uchun
              </li>
              <li class="our-courses-slider__info-list__item">
                Kurs davomiyligi: 5 ta bosqich, 1 ta bosqich - 3 oy
              </li>
              <li class="our-courses-slider__info-list__item">
                Minimal bosqich: Noldan yoki undan yuqori
              </li>
            </ul>
          </div>
        </swiper-slide>
        <swiper-slide>
          <div class="our-courses-slider__body">
            <div class="our-courses-slider__icon">
              <img src="../assets/images/icons/kitchen.svg" alt="Kitchen" />
            </div>
            <h2 class="our-courses-slider__title">Pazandachilik</h2>
            <ul class="our-courses-slider__info-list">
              <li class="our-courses-slider__info-list__item">
                Pazandachilik kurslarimizda barcha mahsulotlar markazimiz
                tomonidan taqdim qilinadi.
              </li>
              <li class="our-courses-slider__info-list__item">
                Kurs davomiyligi: 1 oy
              </li>
              <li class="our-courses-slider__info-list__item">
                Minimal bosqich: Noldan yoki undan yuqori
              </li>
            </ul>
          </div>
        </swiper-slide>
        <swiper-slide>
          <div class="our-courses-slider__body">
            <div class="our-courses-slider__icon">
              <img src="../assets/images/icons/web.svg" alt="Web" />
            </div>
            <h2 class="our-courses-slider__title">Web dasturlash</h2>
            <ul class="our-courses-slider__info-list">
              <li class="our-courses-slider__info-list__item">
                Web dasturlash kursimiz amaliyotga moslashgan va siz portfolio
                bilan tamomlaysiz kursni.
              </li>
              <li class="our-courses-slider__info-list__item">
                Kurs davomiyligi: 6 ta bosqich, 1 ta bosqich - 1 oy
              </li>
              <li class="our-courses-slider__info-list__item">
                Minimal bosqich: Noldan yoki undan yuqori
              </li>
            </ul>
          </div>
        </swiper-slide>
      </swiper>
      <div class="our-courses-slider__btn _btn">Kursga yozilish</div>
    </div>
  </div>
</template>

<script>
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";

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
    };
  },
};
</script>
