<template>
  <div id="app">
    <header class="header">
      <div class="header__wrap">
        <div class="header__logo">
          <div class="logo">
            <img src="./assets/logo.svg" alt="">
          </div>
        </div>
        <button class="header__burger" :class="{'is-active' : burgerOpen}" @click="toggleMobileMenu">
          <img v-if="burgerOpen" src="./assets/close.svg" alt="">
          <img v-else src="./assets/burger.svg" alt="">
        </button>
      </div>
      <div class="header__nav" :class="{'is-showing' : burgerOpen}">
        <nav class="header__menu">
          <ul class="header__menu-list">
            <li class="header__menu-item">
              <a class="header__menu-link">About</a>
            </li>
            <li class="header__menu-item has-submenu" @click="revealSub">
              <div class="header__sub-wrap">
                <span class="header__menu-link">Help</span>
                <span class="header__menu-pointer" :class="{'is-active' : revealedSub}">
                  <img src="./assets/pointer.svg" alt="">
                </span>
              </div>
              <div class="header__submenu" :class="{'is-revealed' : revealedSub}">
                <ul class="header__submenu-list">
                  <li class="header__submenu-item">
                    <a href="#" class="header__submenu-link">User Guide</a>
                  </li>
                  <li class="header__submenu-item">
                    <a href="#" class="header__submenu-link">Contact Support</a>
                  </li>
                </ul>
              </div>
            </li>
            <li class="header__menu-item">
              <a class="header__menu-link">Features</a>
            </li>
          </ul>
        </nav>
        <button class="button button_view_primary button_type_default header__signup">Sign Up</button>
      </div>
    </header>
    <main>
      <section class="features">
        <div class="features__heading">
          <h1>Features</h1>
          <p class="features__desc">Some of&nbsp;the features and advantages that we&nbsp;provide for those of&nbsp;you who store data in&nbsp;this Data Warehouse.</p>
        </div>
        <div class="features__box">
          <div class="features__list">
            <div class="swiper-container">
              <div class="swiper-wrapper">
                <div class="features__item swiper-slide">
                  <div class="feature">
                    <div class="feature__wrapper">
                      <h2 class="feature__title">First Feature</h2>
                      <p>Little Red Cap opened her eyes and when she saw the sunbeams dancing to and fro through the trees and how the ground was covered with beautiful flowers.</p>
                      <a href="#" class="link">Learn more</a>
                      <div class="feature__number">1</div>
                    </div>
                  </div>
                </div>
                <div class="features__item swiper-slide">
                  <div class="feature">
                    <div class="feature__wrapper">
                      <h2 class="feature__title">Second Feature</h2>
                      <p>Each time she picked one she thought that she could see an even more beautiful one a little way off, and she ran after it, going further and further into the woods.</p>
                      <a href="#" class="link">Learn more</a>
                      <div class="feature__number">2</div>
                    </div>
                  </div>
                </div>
                <div class="features__item swiper-slide">
                  <div class="feature">
                    <div class="feature__wrapper">
                      <h2 class="feature__title">Third Feature</h2>
                      <p>The wolf pressed the latch, and the door opened. He stepped inside, went straight to the grandmother's bed, and ate her up.</p>
                      <a href="#" class="link">Learn more</a>
                      <div class="feature__number">3</div>
                    </div>
                  </div>
                </div>
                <div class="features__item swiper-slide">
                  <div class="feature">
                    <div class="feature__wrapper">
                      <h2 class="feature__title">Fourth Feature</h2>
                      <p>Little Red Cap had run after the flowers. After she had gathered so many that she could not carry any more, she remembered her grandmother.</p>
                      <a href="#" class="link">Learn more</a>
                      <div class="feature__number">4</div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="features__pagination">
            <ul class="features__dots">
              <li class="features__dot is-active"></li>
              <li class="features__dot"></li>
              <li class="features__dot"></li>
            </ul>
          </div>
        </div>
      </section>
    </main>
    <footer class="footer">
      <div class="footer__links">
         <div class="footer__logo">
          <img src="./assets/logo-inverse.svg" alt="">
        </div>
        <nav class="footer__menu">
          <ul class="footer__menu-list">
            <li class="footer__menu-item"><a href="#" class="footer__menu-link">About Us</a></li>
            <li class="footer__menu-item"><a href="#" class="footer__menu-link">Privacy Policy</a></li>
          </ul>
        </nav>
      </div>
      <form action="/" class="footer__signup">
        <input type="email" class="input input_type_default input_width_available" placeholder="Enter your email">
        <button type="submit" class="button button_type_default button_view_secondary footer__signup-submit">Sign Up Now</button>
      </form>
    </footer>
  </div>
</template>

<script>
import './assets/main.scss';

import Swiper from 'swiper';

export default {
  name: 'App',
  data() {
    return {
      burgerOpen: false,
      revealedSub: false,
    };
  },
  methods: {
    toggleMobileMenu() {
      this.burgerOpen = !this.burgerOpen;
    },
    revealSub() {
      this.revealedSub = !this.revealedSub;
    },
  },
  mounted() {
    const swiper = new Swiper('.swiper-container', {
      slidesPerView: 1,
      spaceBetween: 50,
      loop: true,
      speed: 1000,
      autoplay: {
        delay: 3000,
      },
      pagination: {
        el: '.features__dots',
        type: 'bullets',
        bulletClass: 'features__dot',
        bulletActiveClass: 'is-active',
        clickable: true,
      },
      breakpoints: {
        1650: {
          slidesPerView: 2,
          slidesPerGroup: 2,
          spaceBetween: 50,
          parallax: false,
        },
      },
    });
    swiper.init();
  },
};
</script>
