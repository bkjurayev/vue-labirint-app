<template>
  <section id="advantages" class="main__advantages advantages">
    <div class="advantages__container _container">
      <h1 class="advantages__title _title">
        "Labirint" o'quv markazi afzalliklari
      </h1>
      <p class="advantages__subtitle">
        Har bir o'quvchimiz quyidagi afzalliklarga ega bo'ladi
      </p>
      <div class="advantages__body">
        <div class="advantages__list">
          <div class="advantages__item">
            <img src="../assets/images/icons/advantages/Crown.svg" alt="" />
            Academic Support - ikkinchi o'qituvchi xizmati. Darsdan tashqari
            bepul qo'shimcha mashg'ulotlar olish imkoniyati
          </div>
          <div class="advantages__item">
            <img
              src="../assets/images/icons/advantages/CircleWavyCheck.svg"
              alt=""
            />
            Ota-ona va o’quvchi o'z uy vazifalari, baho va natijalarini kuzatib
            borishi uchun maxsus platformada shaxsiy kabinet
          </div>
          <div class="advantages__item">
            <img src="../assets/images/icons/advantages/User.svg" alt="" />
            O'quvchilarni imtihonlarga tayyorlash bo'yicha 3-7 yillik tajribaga
            ega ustozlar (IELTS 8,5 gacha)
          </div>
          <div class="advantages__item">
            <img src="../assets/images/icons/advantages/Flag.svg" alt="" />
            O'zbekiston bo'ylab filiallarga ega, tajriba va ishon
          </div>
          <div class="advantages__item">
            <img
              src="../assets/images/icons/advantages/GraduationCap.svg"
              alt=""
            />
            Tadbirlar - hafta davomida va yakshanba kungi bepul trening,
            master-class, speaking club'lar
          </div>
          <div class="advantages__item">
            <img
              src="../assets/images/icons/advantages/NotePencil.svg"
              alt=""
            />
            O'zini ko'rsatgan o'quvchilar uchun ajoyib takliflar
          </div>
          <div class="advantages__item">
            <img src="../assets/images/icons/advantages/Handshake.svg" alt="" />
            Darsdan tashqari qo'shimcha dars tayyorlash uchun co-working joylar
          </div>
          <div class="advantages__item">
            <img
              src="../assets/images/icons/advantages/IdentificationCard.svg"
              alt=""
            />
            IELTS MOCK CLUB – har yakshanba kuni bepul IELTS treninglari va
            IELTS MOCK imtihoni
          </div>
          <div class="advantages__item">
            <img src="../assets/images/icons/advantages/Users.svg" alt="" />
            Jamoaga qo'shilish - iqdidorlik o'quvchilarni jamoamiz azosi bo'lish
            imkoniyati
          </div>
        </div>
      </div>
      <div class="advantages__btn _btn" @click="isOpenModal = !isOpenModal">Kursga yozilish</div>
    
      <VModal @close="closeModal" :isOpenModal="isOpenModal"/>  
    
    </div>
  </section>
</template>

<script setup>
import VModal from "@/components/v-modal.vue";
import { ref } from "@vue/reactivity";

const isOpenModal = ref(false);
const closeModal = (val) => {
  isOpenModal.value = val;
};
</script>
