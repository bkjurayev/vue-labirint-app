<template>
  <section class="main__courses our-courses">
    <div class="our-courses__container _container">
      <h1 class="our-courses__title _title">
        Xorijiy tillar
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
        
        <swiper-slide v-for="language in languages" :key="language.title">
          <div class="our-courses__slider slider">
            <div class="slider__icon">
              <img :src="language.icon" alt="Eng" />
            </div>
            <h2 class="slider__title">{{ language.title }}</h2>
            <h3 class="slider__price">{{ language.price }} sum</h3>
            <ul class="slider__info-list">
              
              <li class="slider__info-list__item" v-for="advantage, index in language.advantages" :key="index">
                <img src="../assets/images/icons/checked.png" alt="icon" />
                {{advantage}}
              </li>
              
            </ul>
          </div>
        </swiper-slide>
        
      </swiper>
      <div class="slider__btn _btn" @click="isOpenModal = !isOpenModal">Kursga yozilish</div>

      <VModal @close="closeModal" :isOpenModal="isOpenModal"/> 

    </div>
  </section>
</template>

<script>
import VModal from "@/components/v-modal.vue";
import { ref } from "@vue/reactivity";
import { Swiper, SwiperSlide } from "swiper/vue";
import { Pagination } from "swiper";

import "swiper/css";
import "swiper/css/pagination";


export default {
  components: {
    VModal,
    Swiper,
    SwiperSlide,
  },
  setup() {  
    const isOpenModal = ref(false);      
    const languages = [
      {
        title: 'Ingliz tili',
        price: '220 000',
        advantages: [
          "Ingliz tilini noldan yoki ma’lum darajadan o’rganmoqchi bo'lganlar uchun", 
          "Minimal bosqich: Noldan yoki undan yuqori", 
        ],
        icon: require('../assets/images/icons/ingliz-tili.png'),
      },
      {
        title: 'Rus tili',
        price: '220 000',
        advantages: [
          "Rus tilini tajribali ustozdan o'rganing", 
          "Minimal bosqich: Noldan yoki undan yuqori", 
        ],
        icon: require('../assets/images/icons/ingliz-tili.png'),
      },
      {
        title: 'Koreys tili',
        price: '350 000',
        advantages: [
          "Koreys tilini qulay muhitda o'rganing", 
          "Minimal bosqich: Noldan yoki undan yuqori", 
        ],
        icon: require('../assets/images/icons/ingliz-tili.png'),
      },
      {
        title: 'Nemis tili',
        price: '350 000',
        advantages: [
          "Nemis tilini o'rganish endi qiyin emas, Labirint sizga ajoyib imkoniyat", 
          "Minimal bosqich: Noldan yoki undan yuqori", 
        ],
        icon: require('../assets/images/icons/ingliz-tili.png'),
      },
      {
        title: 'Arab tili',
        price: '220 000',
        advantages: [
          "Arab tilida o'z bilimingizni va ko'nikmalaringizni rivojlantiring", 
          "Minimal bosqich: Noldan yoki undan yuqori", 
        ],
        icon: require('../assets/images/icons/ingliz-tili.png'),
      },
      {
        title: 'Yapon tili',
        price: '220 000',
        advantages: [
          "Yapon tilida o'z bilimingizni va ko'nikmalaringizni rivojlantiring", 
          "Minimal bosqich: Noldan yoki undan yuqori", 
        ],
        icon: require('../assets/images/icons/ingliz-tili.png'),
      },
      {
        title: 'Turk tili',
        price: '220 000',
        advantages: [
          "Turk tilida o'z bilimingizni va ko'nikmalaringizni rivojlantiring", 
          "Minimal bosqich: Noldan yoki undan yuqori", 
        ],
        icon: require('../assets/images/icons/ingliz-tili.png'),
      },
    ];
    const closeModal = (val) => {
      isOpenModal.value = val;
    };
    const onSwiper = (swiper) => {
      // console.log(swiper);
      return swiper
    };      
    const onSlideChange = () => {
      // console.log("slide change");
    };
    return {
      isOpenModal,
      closeModal,
      onSwiper,
      onSlideChange,
      modules: [Pagination],
      languages
    };
  },
};
</script>
