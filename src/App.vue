<template>
  <div id="app">
    <nav class="nav container">
      <a class="nav__logo" href="#">
        <img class="nav__img" src="../public/logo.png" alt="Piroll">
      </a>
        <ul
          class="nav__items"
          :class="{'nav__mobile' : showMobileMenu}"
        >
          <li v-for="(item, index) in menu" :key="index" class="nav__item">
            <a 
              :class="{'nav__link-active' : index === 0}"
              class="nav__link" 
              href="#"
            >
              {{ item }}
            </a>
          </li>
        </ul>
      <button @click="showMobileMenu = !showMobileMenu" type="button" class="nav__burger">
        <span v-if="!showMobileMenu" class="nav__burger-item"></span>
        <span v-else class="nav__burger-close"></span>

      </button>
    </nav>
    <div class="main-block">
      <div class="main-block__info">
        <h1 class="main-block__title">We Design and Develop</h1>
        <p class="main-block__description">
          We are a new design studio based in USA. We have over 
          20 years of combined experience, and know a thing or two 
          about designing websites and mobile apps.
        </p>
        <a class="link main-block__link" href="#">Contact us</a>
        </div>
    </div>
    <footer style="height:250px;"></footer>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      menu: [
        'home',
        'about',
        'work',
        'process',
        'services',
        'testimonials',
        'contact'
      ],
      showMobileMenu: false
    }
  }
}
</script>

<style lang="scss">
  @import './assets/scss/style';

  .link {
    font-size: 12px;
    padding: 20px 50px;
    text-decoration: none;
    text-transform: uppercase;
    color: #fff;
    background-color: $mainColor;
  }

  .nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: transparent;
    position: relative;
    z-index: 4;

    @include max-width-750 {
      margin: 30px 0 0 0;
    }

    &__logo {
      display: inline-block;
      margin: 38px 0 0 8px;

      @include max-width-750 {
        margin: 0;
      }
    }

    &__img {

    }

    &__items {
      display: flex;
      justify-content: center;
      align-items: center;
      margin: 29px -38px 0 0;
      padding: 0;
      list-style: none;

      @include max-width-1260 {
        margin: 29px 0 0 0;
      }

      @include max-width-750 {
        display: none;
      }
    }

    &__mobile {
      display: flex;
      flex-direction: column;
      position: fixed;
      top: 0;
      left: 0;
      z-index: 5;
      width: 100%;
      height: 100vh;
      overflow: scroll;
      background-color: #5f5f5f;
      margin: 0;
      padding: 60px 0 0 0;
    }

    &__item {

    }

    &__link {
      display: inline-block;
      text-decoration: none;
      text-transform: uppercase;
      color: #fff;
      font-size: 12px;
      font-weight: bold;
      margin: 0 0 0 37px;

      @include max-width-750 {
        font-size: 20px;
        margin: 0 0 20px 0;
      }
    }

    &__link-active {
      color: $mainColor;
    }

    &__burger {
      display: flex;
      justify-content: center;
      align-items: center;
      position: relative;
      border: 1px solid #fff;
      outline: none;
      cursor: pointer;
      background-color: transparent;
      width: 35px;
      height: 30px;
      z-index: 6;

      @include min-width-751 {
        display: none;
      }
    }

    &__burger-item{
      display: inline-block;
      position: relative;
      width: 30px;
      height: 1px;
      background-color: #fff;
    }

    &__burger-item::before,
    &__burger-item::after {
      content: '';
      position: absolute;
      width: 21px;
      height: 1px;
      background-color: #fff;
      left: 50%;
      transform: translate(-50%, 0);
    }

    &__burger-item::before {
      top: -7px;
    }

    &__burger-item::after {
      top: 7px;
    }
  
    &__burger-close::before,
    &__burger-close::after {
      content: '';
      position: absolute;
      width: 30px;
      height: 1px;
      background-color: #fff;
      top: 50%;
      left: 2px;
      transform-origin: 50% 50%;
    }

    &__burger-close::before {
      transform: rotate(45deg);
    }

    &__burger-close::after {
      transform: rotate(-45deg)
    }

  }

  .main-block {
    position: absolute;
    top: 0;
    left: 0;
    background-image: url(./assets/images/main_img.jpg);
    background-repeat: no-repeat;
    background-size: cover;
    background-position: 50%;
    width: 100%;
    height: 670px;
    z-index: 2;

    &__info {
      position: absolute;
      top: 202px;
      right: 387px;
      z-index: 4;
      text-align: right;

      @include max-width-1190 {
        width: 80%;
        right: 0;
        left: 50%;
        transform: translate(-50%, 0);
        text-align: center;
      }

      @include max-width-550 {
        top: calc(50% - 200px);
      }
    }

    &__title {
      font-size: 38px;
      color: #1d1d1d;

    }

    &__description {
      font-size: 18px;
      max-width: 470px;
      color: #fff;
      line-height: 28px;
      margin: -3px -5px 0 0;

      @include max-width-1190 {
        max-width: 100%;
        margin: 0 0 25px 0;
      }
    }

    &__link {
      display: inline-block;
      margin: 6px 276px 0 0;

      @include max-width-1190 {
        margin: 0;
      }
    }
  }

  .main-block::before {
    content: '';
    position: absolute;
    width: 100%;
    height: 670px;
    z-index: 3;
    background-color: rgba(12, 12, 12, 0.5);
  }

</style>
