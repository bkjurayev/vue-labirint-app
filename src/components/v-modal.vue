<template>
  <div
    class="modal"
    :class="{ _show: isOpenModal }"
    @click="close"
  >
    <form class="modal__form" action="" @click.stop>
      <div class="modal__input">
        <label for="name">Ism</label>
        <input name="name" type="text" v-model="inputName" @input.prevent/>
      </div>
      <div class="modal__input">
        <label for="surname">Sharifingiz</label>
        <input name="surname" type="text" v-model="inputSurName" />
      </div>
      <div class="modal__input">
        <label for="phone">Telefon raqamingiz</label>
        <input name="phone" type="number" v-model="inputPhone" />
      </div>

      <div
        class="btn-disabled"
        v-if="inputName == '' || inputPhone == ''"
      >
        <span>Юбориш</span>
      </div>
      <div
        class="_btn"
        @click="onClickSendToTg"
        v-if="inputName != '' && inputPhone != ''"
      >
        <span v-if="!loading">Юбориш</span>
        <div v-else class="looping-rhombuses-spinner">
          <div class="rhombus"></div>
          <div class="rhombus"></div>
          <div class="rhombus"></div>
        </div>
      </div>
    </form>
  </div>
</template>

<script>
import axios from "axios";
import { ref } from "vue";
// import { watch } from '@vue/runtime-core'


export default {
  props: {
    isOpenModal: {
      type: Boolean,
      default: false,
    },
  },
  setup() {    
    const inputName = ref("");
    const inputSurName = ref("");
    const inputPhone = ref("");
    const TOKEN = "5336070499:AAFrn3cc5vInWMLnqbqHB7uC9BZRuxXk7dE";
    const CHAT_ID = "-1001792646372";
    const URI_API = `https://api.telegram.org/bot5336070499:AAFrn3cc5vInWMLnqbqHB7uC9BZRuxXk7dE/sendMessage`;
    const loading = ref(false);

    // watch(() => this.isOpenModal, () => {  
    //   if (document.querySelector('body').style.overflow != 'hidden') {
    //     document.querySelector('body').style.overflow = 'hidden'
    //   } else {
    //     document.querySelector('body').style.overflow = 'inherit'
    //   }
    // })

    return {
      inputName,
      inputSurName,
      inputPhone,
      TOKEN,
      CHAT_ID,
      URI_API,
      loading,
    };
  },
  watch: { 
    isOpenModal() {
      if (document.querySelector('body').style.overflow != 'hidden') {
        document.querySelector('body').style.overflow = 'hidden'
      } else {
        document.querySelector('body').style.overflow = 'inherit'
      }
    }
  },
  methods: {
    close() {
      this.$emit("close", false);
    },
    onClickSendToTg() {
      this.loading = true;
      axios
        .post(this.URI_API, {
          chat_id: this.CHAT_ID,
          parse_mode: "html",
          text: `<b>Name:</b>${this.inputName}\n<b>Surname:</b>${this.inputSurName}\n<b>Phone:</b>${this.inputPhone}`,
        })
        .then(() => {
          this.loading = false;
          this.inputName = "";
          this.inputSurName = "";
          this.inputPhone = "";
        });
      setTimeout(() => this.close(), 1000)      
    },
  },
  created() {
    let that = this;
    document.addEventListener("keyup", function (evt) {
      if (evt.keyCode === 27) {
        that.close();
      }
    });
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
