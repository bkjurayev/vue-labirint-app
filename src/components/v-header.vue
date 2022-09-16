<template>
  <header class="header">
    <div class="header__container _container">
      <div class="header__body">
        <div class="header__logo">
          <router-link to="/">
            <img src="../assets/images/Logo-small.png" alt="Logo" />
          </router-link>
        </div>
        <nav
          class="header__navbar navbar"
          :class="{ activeBurger: isOpenBurger }"
        >
          <ul class="navbar__lists">
            <li class="navbar__item">
              <router-link
                :to="{ name: home, hash: '#professions' }"
                class="navbar__link"
                @click="onClickBurgerLink"
                >Kusrlar</router-link
              >
            </li>
            <li class="navbar__item">
              <router-link
                :to="{ name: home, hash: '#our-team' }"
                class="navbar__link"
                @click="onClickBurgerLink"
                >Jamoa</router-link
              >
            </li>
            <li class="navbar__item">
              <a
                href="https://t.me/labirint_oquv_markazi"
                class="navbar__link"
                target="_blank"
                @click="onClickBurgerLink"
                >Yangiliklar</a
              >
            </li>
            <li class="navbar__item">
              <a
                href="../assets/test.pdf"
                class="navbar__link oferta"
                target="_blank"
                @click="onClickBurgerLink"
                >Oferta</a
              >
            </li>
            <!-- <li>
              <a @click.prevent="window.open('test.pdf', '_blank')">Oferta-2</a>
            </li> -->
          </ul>
        </nav>
        <div class="header__contacts contacts">
          <div class="contacts__item phone">
            <a href="tel:+99884748080" class="phone__link">
              <span class="phone__icon">
                <img src="../assets/images/icons/call.png" alt="Phone" />
              </span>
              <span class="phone__number">(88) 474 8080</span>
            </a>
          </div>
          <div class="contacts__item btn-accaunt _btn">
            <img src="../assets/images/icons/user-large-solid.svg" alt="User" />
            <span>Shaxsiy kabinet</span>
          </div>
          <div class="contacts__item btn-pay _btn">
            <img src="../assets/images/icons/paypal-brands.svg" alt="Payment" />
            <span>Pay online</span>
          </div>
        </div>
        <div
          class="header__burger burger"
          :class="{ _active: isOpenBurger }"
          @click="onClickBurger"
        >
          <span class="burger__item"></span>
          <span class="burger__item"></span>
          <span class="burger__item"></span>
        </div>
      </div>
    </div>
  </header>
</template>

<script setup>
import { ref } from "vue";
// import { useWindowScroll } from '@vueuse/core';

const isOpenBurger = ref(false);
const onClickBurger = () => {
  isOpenBurger.value = !isOpenBurger.value
  document.body.classList.toggle("_lock")
};
const onClickBurgerLink = () => {
  isOpenBurger.value = false
  document.body.classList.remove("_lock")
};

// const { y } = useWindowScroll();

// const router = new VueRouter({
//   scrollBehavior(to, from) {
//     return { x: 0, y: 300}
//   }
// })
</script>
