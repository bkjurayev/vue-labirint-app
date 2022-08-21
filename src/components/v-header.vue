<template>
  <header class="header">
    <div class="header__container _container">
      <div class="header__body">
        <div class="header__logo">
          <img src="../assets/images/Logo-small.png" alt="Logo" />
        </div>
        <nav 
          class="header__navbar navbar"
          :class="{activeBurger: isOpenBurger}"
        >
          <ul class="navbar__lists">
            <li class="navbar__item">
              <a href="" class="navbar__link">Kusrlar</a>
            </li>
            <li class="navbar__item">
              <a href="" class="navbar__link">Jamoa</a>
            </li>
            <li class="navbar__item">
              <a href="" class="navbar__link">Yangiliklar</a>
            </li>
            <li class="navbar__item">
              <a href="" class="navbar__link">Blog</a>
            </li>
            <li class="navbar__item">
              <a href="" class="navbar__link oferta">Oferta</a>
            </li>
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
          :class="{_active: isOpenBurger}"
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
import { ref } from 'vue';


const isOpenBurger = ref(false)
const onClickBurger = (e) => {
  isOpenBurger.value = !isOpenBurger.value 
  document.body.classList.toggle('_lock')
  console.log(e);
}

const form = document.querySelector('.excursion__form')
console.log(form);
</script>