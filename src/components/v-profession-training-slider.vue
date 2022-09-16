<template>
  <section id="professions" class="main__courses our-courses">
    <div class="our-courses__container _container">
      <h1 class="our-courses__title _title">Kasbga yo'naltirilgan kurslar</h1>
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
        <swiper-slide
          v-for="job in jobs"
          :key="job.title"
          @click="onSelectJob(job), isOpenModalSlider = !isOpenModalSlider"
        >
          <div class="our-courses__slider slider">
            <div class="slider__icon">
              <img :src="job.icon" alt="img" />
            </div>
            <h2 class="slider__title">{{ job.title }}</h2>
            <h3 class="slider__price">{{ job.price }} so'm</h3>
            <ul class="slider__info-list">
              <li
                class="slider__info-list__item"
                v-for="(advantage, index) in job.advantages"
                :key="index"
              >
                <img src="../assets/images/icons/checked.png" alt="check" />
                {{ advantage }}
              </li>
            </ul>
          </div>
        </swiper-slide>
      </swiper>

      <div class="slider__btn _btn" @click="isOpenModal = !isOpenModal">
        Kursga yozilish
      </div>
      
      <div
        class="our-courses__slider__modal slider-modal"
        :class="{ _show: isOpenModalSlider }"
        @click.stop="isOpenModalSlider = !isOpenModalSlider"
      >
        <div class="slider-modal__body">
          <div class="slider-modal__form">            
            <p>{{ job.description }}</p>
          </div>
        </div>
      </div>

      <VModal @close="closeModal" :isOpenModal="isOpenModal" />
    </div>
  </section>
</template>

<script>
import { ref } from "vue";
import { Swiper, SwiperSlide } from "swiper/vue";
import { Pagination } from "swiper";

import VModal from "./v-modal.vue";

import "swiper/css";
import "swiper/css/pagination";

export default {
  components: {
    Swiper,
    SwiperSlide,
    VModal,
  },
  setup() {
    const isOpenModalSlider = ref(false);
    const isOpenModal = ref(false);    
    let job = ref([]);
    const jobs = [
      {
        title: "Web dasturlash",
        price: "500 000",
        advantages: [
          "Dasturlashni o'rganish bilan siz, o'zingiz uchun yorqin kelajakni taminlaysiz",
          "Katta daromad topish va texnologik yangiliklarni analiz qila olish",
          "Raqamli dunyoda faol bo'lish uchun bu bilimlar sizga kerak",
        ],
        description: "",
        icon: require("../assets/images/icons/checked.png"),
      },
      {
        title: "Web design",
        price: "500 000",
        advantages: [
          "Web dizaynerlik sohasi orqali siz yahshi daromad topish bilan birga qulay ish grafikiga ega bo'lasiz.",
          "Bu soha egalari tartibli va didli insonlar hisoblanadi.",
        ],
        description: "",
        icon: require("../assets/images/icons/checked.png"),
      },
      {
        title: "Graphic design",
        price: "500 000",
        advantages: [
          "Grafik dizaynerlik sohasi orqali siz yahshi daromad topish bilan birga qulay ish grafikiga ega bo'lasiz.",
          "Ijodkor va go'zallikni sevuvchi insonlar bu sohada katta natijalarga erishishadi.",
        ],
        description: "",
        icon: require("../assets/images/icons/checked.png"),
      },
      {
        title: "SMM",
        price: "500 000",
        advantages: [
          "Juda katta tezlikda talab ortib borayotgan bu soha Uzbekiston bozorida qanchalik kerakligini isbotladi.",
          "Sohani egallab siz yahshi daromad va ajoyib jamoa a'zosi bolasiz.",
        ],
        description: "",
        icon: require("../assets/images/icons/checked.png"),
      },
      {
        title: "Pazandachilik",
        price: "370 000",
        advantages: [
          "Pishir kuydir doim insonlarning kongliga yo'l topishning eng samarali usuli bo'lgan.",
          "Yahshi pazanda kelinga bo'lgan talab doimo yuqori bo'ladi bu fakt ;)",
        ],
        description: "1 va 2 oylik tezkor kurslarimiz. Haftada 3 kun 2 soatdan 370.000so'm. Barcha mahsulotlarimiz o'quv markazi tomonidan beriladi. 50 xil turdagi narsalar o'rgatiladi: 20xil pishiriq, 10xil to'rt, 10xil salat, 10xil ovqat. Bitiruvchilarimizga o'quv markazi tomonidan sertifikat beriladi.",
        icon: require("../assets/images/icons/checked.png"),
      },
      {
        title: "Uy hamshirasi",
        price: "350 000",
        advantages: [
          "Insonlar hayotida doim bir birlariga yordam berishadi. Hamshira bo'la turib o'z yordamingizni ayamasangiz bu juda qadrli.",
          "Hamshiralar zamonga moslashib, yanayam ko'proq ko'nikmalarni egallashmoqda va shifokorlarning ko'p vazifalarini o'zlari uddalashmoqda",
        ],
        description: "1 oylik va 2 oylik tezkor kurslarimiz 350 ming so'm. Kursimizda tomirga tushish, yonboshga tushish, puls o'lchash, va 50xil turdagi kasalliklarni kelib chiqishi va ularni davolash yo'llari o'rgatiladi. Bitiruvchilarimizga o'quv markazimiz tomonidan sertifikat va ixtiyoriy xolda diplom beriladi.",
        icon: require("../assets/images/icons/checked.png"),
      },
      {
        title: "Massaj",
        price: "220 000",
        advantages: [
          "Massaj kursini tugatib siz o'z farzandlaringizni jismonan sog'lom va ko'rkam ulgayishini kafolatlaysiz.",
        ],
        description: "",
        icon: require("../assets/images/icons/checked.png"),
      },
      {
        title: "Buxgalteriya 1C",
        price: "350 000",
        advantages: [
          "Pul ko'p bo'lishi yahshi, lekin uni tog'ri boshqarish bu bitta muammo.",
          "Siz moliyaviy savodhonligingizni oshirsangiz katta pullarni oqimini tahlil qilish va yahshi daromad topishingiz mimkin.",
        ],
        description: "2 oylik tezkor kurslarimiz haftada 3 kun 2 soatdan 400.000so'm Ushbu 2 oylik kursimizni tugatgandan so'ng 3 oyda 1C dasturi o'rgatiladi. 1C dasturi uchun oylik to'lov 600.000so'mni tashkil qiladi.",
        icon: require("../assets/images/icons/checked.png"),
      },
      {
        title: "Chevarchilik",
        price: "220 000",
        advantages: [
          "Bilasizmi insonni qo'li gul agar chevar bo'lsangiz sizdan yahshi inson yo'q go'yoki.",
          "Chevarchilikni o'rganib insonlarni eng yahshi kunlarida o'zlariga bo'lgan ishonchini yanada yuqori bo'lishiga yordam bergan bo'lasiz.",
        ],
        description: "2 oylik tezkor kurslarimiz haftada 3 kun 2 soatdan bo'ladi 220.000so'm Ushbu kursimiz davomida bichish, tikish va andozalar bilan ishlash hamda turli xildagi kiyimlarni modellashtirishni o'rganasiz. Bitiruvchilarimizga sertifikat beriladi.",
        icon: require("../assets/images/icons/checked.png"),
      },
      {
        title: "Elita parda",
        price: "220 000",
        advantages: [
          "Siz kursni tugatib ajoyib pardalar tikib insonlarni uylarini ajoyib ko'rinishga keltirasiz.",
          "Daromadingizham mo'maygina bo'ladi bu sohada.",
        ],
        description: "",
        icon: require("../assets/images/icons/checked.png"),
      },
      {
        title: "Karving",
        price: "220 000",
        advantages: [
          "Ijodkor insonmisiz bu soha siz uchun.",
          "Hammani hayron qoldirish vaqti keldi.",
        ],
        description: "1 oylik tezkor kurslarimiz 220.000so'm Ushbu kursimizda har xil turdagi meva va sabzavotlardan dekoratsiya yasash o'rgatiladi.",
        icon: require("../assets/images/icons/checked.png"),
      },
      {
        title: "Kompyuter",
        price: "350 000",
        advantages: [
          "Komyuter butun hayotimizga kirib bo'ldi. Kelajakda kompyutersiz biron soha rivojlanmaydi.",
          "O'zingizni keraklik va muhim kadr ekanligingizga ishontirish uchunham bu bilimlar zarur.",
        ],
        description: "1 oylik tezkor kurslarimiz har kuni 2 soatdan bo'lib o'tadi. 350.000so'm oylik to'lovi. Ushbu kursimizda Word, Exel, PowerPoint dasturlari va kompyuterda ishlash ko'nikmalari o'rgatiladi.",
        icon: require("../assets/images/icons/checked.png"),
      },
      {
        title: "Ayollar sartaroshi",
        price: "220 000",
        advantages: ["Sohani o'rganing va ishlamasdan pul toping"],
        description: "Ayollar sartaroshi 1 oylik tezkor kurs bo'lib 220.000so'm oylik to'lovi. Ushbu kursimizda turli xil makiyajlar va 100 xildan ortiq soch turmaklari o'rgatiladi. Bitiruvchilarimizga o'quv markaz tomonidan sertifikat va ixtiyoriy diplom beriladi.",
        icon: require("../assets/images/icons/checked.png"),
      },
    ];
    const closeModal = (val) => {
      isOpenModal.value = val;
    };
    const onSelectJob = (val) => {
      job.value = val
    } 

    const onSwiper = (swiper) => {
      // console.log(swiper);
      return swiper;
    };
    const onSlideChange = () => {
      // console.log("slide change");
    };
    return {
      isOpenModalSlider,
      isOpenModal,
      onSelectJob,
      closeModal,
      job,
      jobs,
      onSwiper,
      onSlideChange,
      modules: [Pagination],
    };
  },
};
</script>
