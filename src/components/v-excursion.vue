<template>
  <section id="excursion" class="excursion">
    <div class="excursion__container _container">
      <h1 class="excursion__title _title">
        O’quv markazimiz bo'ylab ekskursiyaga marhamat!
      </h1>
      <p class="excursion__subtitle">
        Ingliz tili darajangizni bepul tekshirish va o’quv markazlarimizdan
        biriga bepul ekskursiyaga tashrif buyurish uchun o’z ma’lumotlaringizni
        qoldiring
      </p>
      <div class="excursion__body">
        <form action="" class="excursion__form">
            <input class="excursion__form__input" type="text" placeholder="Ism" v-model="inputName">
            <input class="excursion__form__input" type="number" placeholder="Telefon raqamingiz" v-model="inputPhone">
            <textarea  class="excursion__form__input textarea" rows="6" cols="20" placeholder="Fikr va takliflar" v-model="inputDescription"></textarea>                        
            <div
              class="excursion__form__btn _btn btn-disabled"
              v-if="inputName == '' || inputPhone == ''"
            >
              <span>Yuborish</span>
            </div>
            <div
              class="excursion__form__btn _btn"
              @click="onClickSendToTg"
              v-if="inputName != '' && inputPhone != ''"
            >
              <span v-if="!loading">Yuborish</span>
              <div v-else class="looping-rhombuses-spinner">
                <div class="rhombus"></div>
                <div class="rhombus"></div>
                <div class="rhombus"></div>
              </div>
            </div>

            <p class="excursion__form__info">Ma'lumotlaringiz 3-shaxslarga berilmaydi</p>
        </form>
        <div class="excursion__img">
          <img src="../assets/images/labirint.png" alt="Labirint-reception">
        </div>
      </div>
    </div>
  </section>
</template>



<script>
  import axios from "axios";
  import { ref } from "vue";
  
  export default {
    setup() {
      const inputName = ref("");
      const inputPhone = ref("");
      const inputDescription = ref("");
      const TOKEN = "5336070499:AAFrn3cc5vInWMLnqbqHB7uC9BZRuxXk7dE";
      const CHAT_ID = "-1001792646372";
      const URI_API = `https://api.telegram.org/bot5336070499:AAFrn3cc5vInWMLnqbqHB7uC9BZRuxXk7dE/sendMessage`;
      const loading = ref(false);
  
      return {
        inputName,
        inputPhone,
        inputDescription,
        TOKEN,
        CHAT_ID,
        URI_API,
        loading,
      };
    },
    methods: {
      onClickSendToTg() {
        this.loading = true;
        axios
          .post(this.URI_API, {
            chat_id: this.CHAT_ID,
            parse_mode: "html",
            text: `<b>Name:</b>${this.inputName}\n<b>Phone:</b>${this.inputPhone}\n<b>Description:</b>${this.inputDescription}`,
          })
          .then(() => {
            this.loading = false;
            this.inputName = "";
            this.inputPhone = "";
            this.inputDescription = "";
          });
        setTimeout(() => this.close(), 1000)      
      },
    },
  };
  </script>


<style lang="scss">
	.looping-rhombuses-spinner, .looping-rhombuses-spinner * {
      box-sizing: border-box;
    }

    .looping-rhombuses-spinner {
      width: calc(15px * 4);
      height: 15px;
      position: relative;
    }

    .looping-rhombuses-spinner .rhombus {
      height: 15px;
      width: 15px;
      background-color: #000;
      left: calc(15px * 4);
      position: absolute;
      margin: 0 auto;
      border-radius: 2px;
      transform: translateY(0) rotate(45deg) scale(0);
      animation: looping-rhombuses-spinner-animation 2500ms linear infinite;
    }

    .looping-rhombuses-spinner .rhombus:nth-child(1) {
      animation-delay: calc(2500ms * 1 / -1.5);
    }

    .looping-rhombuses-spinner .rhombus:nth-child(2) {
      animation-delay: calc(2500ms * 2 / -1.5);
    }

    .looping-rhombuses-spinner .rhombus:nth-child(3) {
      animation-delay: calc(2500ms * 3 / -1.5);
    }

    @keyframes looping-rhombuses-spinner-animation {
      0% {
        transform: translateX(0) rotate(45deg) scale(0);
      }
      50% {
        transform: translateX(-233%) rotate(45deg) scale(1);
      }
      100% {
        transform: translateX(-466%) rotate(45deg) scale(0);
      }
    }
</style>