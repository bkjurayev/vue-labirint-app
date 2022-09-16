<template>
  <div class="main__container _container">
    <div class="main__top top-main">
      <div class="top-main__content">
        <h1 class="top-main__content__title">
          <strong>Qimmatli vaqtingizni o'z kelajagingiz uchun tiking.</strong>
          Labirint o'quv markazi orzular sari birinchi qadam.
        </h1>
        <p class="top-main__content__subtitle">
          Labirint o’quv markazida faqat aniq maqsadga ega o'quvchilarni
          uchratasiz.
        </p>
        <div
          class="top-main__content__btn _btn"
          @click="isOpenModal = !isOpenModal"
        >
          Birinchi darsga yozilish
        </div>
      </div>
      <div class="top-main__video">
        <img
          src="../assets/images/student.png"
          alt="Student"
          class="top-main__video__img"
        />
        <div class="top-main__video__btn">
          <div
            class="top-main__video__btn__img"
            @click="isOpenModalVideo = !isOpenModalVideo"
          >
            <img src="../assets/images/icons/play.svg" alt="play" />
          </div>
          <p class="top-main__video__btn__text">
            O'quv markazimiz haqida bilishni hoxlaysizmi?
          </p>
        </div>
        <div
          class="top-main__video__modal video-modal"
          :class="{ _show: isOpenModalVideo }"
          @click.stop="isOpenModalVideo = !isOpenModalVideo"
        >
          <div class="video-modal__body">
            <iframe
              width="560"
              height="315"
              src="https://www.youtube.com/embed/0QKbh74HhbY"
              title="YouTube video player"
              frameborder="0"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen
            ></iframe>
          </div>
        </div>
      </div>
    </div>

    <VModal @close="closeModal" :isOpenModal="isOpenModal" />
  </div>
</template>

<script>
import VModal from "@/components/v-modal.vue";
import { ref } from "@vue/reactivity";

export default {
  components: {
    VModal,
  },
  setup() {
    const isOpenModalVideo = ref(false);
    const isOpenModal = ref(false);
    const closeModal = (val) => {
      isOpenModal.value = val;
    };
    return {
      isOpenModalVideo,
      isOpenModal,
      closeModal,
    };
  },
  created() {
    let that = this;
    document.addEventListener("keyup", function (evt) {
      if (evt.keyCode === 27) {
        that.isOpenModalVideo = false;
      }
    });
  },
};
</script>
