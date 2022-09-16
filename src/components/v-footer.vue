<template>
    <footer class="footer">
        <div class="footer__container _container">
            <div class="footer__body">
                <div class="footer__item logo">
                    <router-link to="/">
                        <img src="../assets/images/Logo.png" alt="logo">
                    </router-link>
                </div>
                <div class="footer__item socials">
                    <a href="https://www.instagram.com/labirint_uz/" target="_blank">
                        <img src="../assets/images/icons/socials/instagram.png" alt="instagram">
                    </a>
                    <a href="https://t.me/labirint_oquv_markazi" target="_blank">
                        <img src="../assets/images/icons/socials/telegram.png" alt="telegram">
                    </a>
                    <img src="../assets/images/icons/socials/facebook.png" alt="facebook">
                </div>
                <div class="footer__item menu-footer">
                    <ul class="menu-footer__list">
                        <li class="menu-footer__list__link">
                            <router-link :to="{name: home, hash: '#professions'}" class="navbar__link">Kusrlar</router-link>                                                        
                        </li>
                        <li class="menu-footer__list__link">
                            <router-link :to="{name: home, hash: '#advantages'}" class="navbar__link">Afzalliklar</router-link>                                                        
                        </li>
                        <li class="menu-footer__list__link">O'quvchilar</li>
                        <li class="menu-footer__list__link">
                            <router-link :to="{name: home, hash: '#excursion'}" class="navbar__link">Ekskursiya</router-link>                            
                        </li>
                        <li class="menu-footer__list__link">Filiallar</li>
                        <li class="menu-footer__list__link">Jamoa</li>
                        <li class="menu-footer__list__link">Ustozlar</li>
                        <li class="menu-footer__list__link">Rahbar</li>
                        <li class="menu-footer__list__link">Tadbirlar</li>
                        <li class="menu-footer__list__link">Yangiliklar</li>
                        <li class="menu-footer__list__link">Blog</li>
                        <li class="menu-footer__list__link">Savollar</li>
                    </ul>
                </div>
            </div>
        </div>
    </footer>
</template>