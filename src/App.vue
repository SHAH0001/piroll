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
    <div class="about-block container">
      <h2 class="about-block__title">About Us</h2>
      <p class="about-block__description">
        Divide have don't man wherein air fourth. Own itself make have night won't make. 
        A you under Seed appear which good give. Own give air without fowl moveth dry first 
        heaven fruit, dominion she'd won't very all.
      </p>
      <img class="about-block__img" :src="getImage('signature.png')" alt="">
    </div>
    <div class="professional-skills">
      <div class="professional-skills__left">
        <div class="professional-skills__wrapper">
          <h3 class="professional-skills__title">Professional Skills</h3>
          <div class="skill-progress">
            <span class="skill-progress__title">UI/UX Design <span class="skill-progress__count">75%</span></span>
            <div class="skill-progress__total">
              <div style="width: 67%;" class="skill-progress__current"></div>  
            </div>
          </div>
          <div class="skill-progress">
            <span class="skill-progress__title">Web development <span class="skill-progress__count">90%</span></span>
            <div class="skill-progress__total">
              <div style="width: 85%;" class="skill-progress__current"></div>  
            </div>
          </div>
          <div class="skill-progress">
            <span class="skill-progress__title">Marketing  <span class="skill-progress__count">65%</span></span>
            <div class="skill-progress__total">
              <div style="width: 56%;" class="skill-progress__current"></div>  
            </div>
          </div>
        </div>
      </div>
      <div class="professional-skills__right"></div>
    </div>
    <div class="about-our-work">
      <div class="container">
        <div class="about-our-work__items">
          <div class="about-our-work__item portfolio">
            <h4 class="about-our-work__conut">548</h4>
            <p class="about-our-work__text">Projects completed</p>
          </div>
          <div class="about-our-work__item clock">
            <h4 class="about-our-work__conut">1465</h4>
            <p class="about-our-work__text">Working hours</p>
          </div>
          <div class="about-our-work__item star">
            <h4 class="about-our-work__conut">612</h4>
            <p class="about-our-work__text">Positive feedbacks</p>
          </div>
          <div class="about-our-work__item like">
            <h4 class="about-our-work__conut">735</h4>
            <p class="about-our-work__text">Happy clients</p>
          </div>
        </div>
      </div>
    </div>
    <div class="gallery">
      <a 
        v-for="(item, index) in 8" 
        :key="index"
        href="#" 
        class="gallery__item"
      >
        <img  
          class="gallery__img" 
          :src="getImage('img_' + item + '.jpg')" 
          alt=""
        />
        <div class="gallery__overlay"></div>
      </a>
    </div>
    <h3 class="load-more">Load more works</h3>
    <div class="our-work">
      <div class="container">
        <h3 class="our-work__title">Our Work Process</h3>
        <p class="our-work__description">
          Was years it seasons was there form he in in them together over that, 
          third sixth gathered female creeping bearing behold years.
        </p>
        <div class="our-work__video-wrapper">
          <video 
            id="mainVideo"
            class="our-work__video" 
            poster="./assets/images/video-poster.jpg" src="./assets/videos/video.mp4"
          ></video>
          <button 
            @click="startStop()" 
            :class="{'video-play' : videoPlay}"
            class="our-work__play-stop" 
            type="button"
          >
            <span :class="{'video-play' : videoPlay}" class="play-stop"></span>
          </button>
        </div>
      </div>
    </div>
    <div class="features">
      <div class="container">
        <div class="features__wrapper">
          <div class="features__item diamond">
            <a href="#" class="features__title">ui / ux design</a>
            <p class="features__description">
              Be set fourth land god darkness 
              make it wherein own
            </p>
          </div>
          <div class="features__item arc">
            <a href="#" class="features__title">web development</a>
            <p class="features__description">
              A she'd them bring void moving 
              third she'd kind fill
            </p>
          </div>
          <div class="features__item phone">
            <a href="#" class="features__title">app / mobile</a>
            <p class="features__description">
              Dominion man second spirit he,
              earth they're creeping
            </p>
          </div>
          <div class="features__item joy">
            <a href="#" class="features__title">game design</a>
            <p class="features__description">
              Morning his saying moveth it 
              multiply appear life be</p>
          </div>
          <div class="features__item plane">
            <a href="#" class="features__title">SEO / marketing</a>
            <p class="features__description">
              Give won't after land fill creeping 
              meat you, may
            </p>
          </div>
          <div class="features__item star">
            <a href="#" class="features__title">photography</a>
            <p class="features__description">
              Creepeth one seas cattle grass 
              give moving saw give
            </p>
          </div>
          <div class="features__item magic-wand">
            <a href="#" class="features__title">graphic design</a>
            <p class="features__description">
              Open, great whales air rule for, 
              fourth life whales
            </p>
          </div>
          <div class="features__item paint-bucket">
            <a href="#" class="features__title">illustrations</a>
            <p class="features__description">
              Whales likeness hath, man kind 
              for them air two won't
            </p>
          </div>
        </div>
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
      showMobileMenu: false,
      videoPlay: false
    }
  },
  methods: {
    getImage(path) {
      return require('./assets/images/' + path);
    },
    startStop() {
      let video = document.getElementById('mainVideo')

      if(video.paused) {
        video.play()
        this.videoPlay = true
      }
      else {
        video.pause()
        this.videoPlay = false
      }
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
      margin: 38px 0 0 -19px;

      @include max-width-1260 {
        margin: 38px 0 0 0;
      }

      @include max-width-750 {
        margin: 0;
      }
    }

    &__items {
      display: flex;
      justify-content: center;
      align-items: center;
      margin: 29px -14px 0 0;
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
      right: 410px;
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
      margin: 6px 280px 0 0;

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

  .about-block {
    text-align: center;
    margin-top: 696px;

    &__title {
      font-size: 30px;
      color: $mainTextColor;
    }  

    &__description {
      font-family: $notoSans;
      font-size: 16px;
      color: $textColor;
      line-height: 24px;
      margin: 0 250px;

      @include max-width-1260 {
        margin: 0;
        padding: 0 15px;
      }
    }

    &__img {
      display: inline-block;
      margin: 35px 0 0 0;
    }
  }

  .professional-skills {
    display: flex;
    margin: 96px 0 0 0;

    @include max-width-850 {
      flex-direction: column;
    }

    &__left {
      width: 50%;
      background-color: #f8f9f9;
      padding: 0 0 129px 0;

      @include max-width-1750 {
        display: flex;
        justify-content: center;
        align-items: center;
        padding: 65px 0;
      }

      @include max-width-850 {
        width: 100%;
      }
    }

    &__wrapper {
      max-width: 520px;
      margin: 158px 0 0 363px;

      @include max-width-1750 {
        width: 100%;
        margin: 0;
        padding: 0 15px;
      }
    }

    &__title {
      font-size: 30px;
      color: #171717;
      margin: 0;
    }

    &__right {
      width: 50%;
      background-image: url(./assets/images/professional_skills.jpg);
      background-repeat: no-repeat;
      background-size: cover;
      background-position: 50%;

      @include max-width-850 {
        width: 100%;
        height: 420px;
      }
    }
  }

  .skill-progress {
    
    margin: 27px 0 35px 0;

    &__title {
      font-size: 12px;
      font-weight: bold;
      color: #000;
      text-transform: uppercase;
    }  

    &__count {
      display: inline-block;
      margin: 0 0 0 27px;
    }

    &__total {
      position: relative;
      max-width: 500px;
      height: 3px;
      background-color: #d8d8d8;
      margin: 16px 0 0 0;
    }

    &__current {
      position: absolute;
      top: 0;
      left: 0;
      width: 0;
      height: 3px;
      background-color: $mainColor;
    }

  }

  .portfolio {
    background-image: url(./assets/images/portfolio.png);
  }

  .clock {
    background-image: url(./assets/images/clock.png);
  }

  .star {
    background-image: url(./assets/images/star.png);
  }

  .like {
    background-image: url(./assets/images/like.png);    
  }

  .about-our-work {
    
    background-color: $mainColor;

    &__items {
      display: flex;
      justify-content: space-between;
      padding: 95px 0 99px 0;
      margin: 0 0 0 -14px;

      @include max-width-1260 {
        margin: 0;
      }

      @include max-width-1190 {
        justify-content: space-around;
        flex-wrap: wrap;
        padding: 50px 0;
      }
    }

    &__item {
      width: 22%;
      background-position: 0 7px;
      background-repeat: no-repeat;
      color: #fff;
      
      @include max-width-1190 {
        width: 45%;
        text-align: center;
        background-position: 25% 7px;
        margin: 20px 0;
      }

      @include max-width-750 {
        background-position: 50% 0;
        padding: 60px 0 0 0;
      }

      @include max-width-550 {
        width: 100%;
      }
    }

    &__conut {
      font-size: 18px;
      margin: 0 0 0 66px;

      @include max-width-750 {
        margin: 0 0 10px 0;
      }
    }

    &__text {
      font-size: 12px;
      margin: 9px 0 0 67px;
      text-transform: uppercase;

      @include max-width-750 {
        margin: 0 0 10px 0;
      }
    }

  }

  .gallery {
    display: flex;
    flex-wrap: wrap;

    &__item {
      position: relative;
      width: 25%;

      @include max-width-850 {
        width: 33.3333%;
      }

      @include max-width-650 {
        width: 50%;
      }

      @include max-width-450 {
        width: 100%;
      }
    }

    &__img {
      display: block;
      width: 100%;
      height: 100%;
    }

    &__overlay {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-color: transparent;
      transition: all .3s;
      background-position: 50%;
      background-repeat: no-repeat;
    }

  }

  .gallery__overlay:hover {
    background-color: rgba(12, 12, 12, 0.5);
    background-image: url(./assets/images/look.png);
  }

  .load-more {
    font-size: 12px;
    color: #8e8e8e;
    cursor: pointer;
    margin: 0;
    text-transform: uppercase;
    background-color: #f5f5f5;
    text-align: center;
    padding: 42px 0;
  }

  .our-work {
    text-align: center;
    margin: 94px 0 0 0;

    &__title {
      font-size: 30px;
      color: $mainTextColor;
      margin: 0 0 27px 0;
    }

    &__description {
      font-size: 16px;
      color: $textColor;
      margin: 0 287px;
      line-height: 24px;

      @include max-width-950 {
        margin: 0;
      }
    }

    &__video-wrapper {
      position: relative;
    }

    &__video {
      display: block;
      width: 100%;
      max-width: 1170px;
      height: 570px;
      margin: 53px 0 0 0;

      @include max-width-950 {
        margin: 0;
        height: auto;
      }
    }

    &__play-stop {
      display: flex;
      justify-content: center;
      align-items: center;
      width: 85px;
      height: 85px;
      background-color: $mainColor;
      border-radius: 50%;
      border: none;
      outline: none;
      position: absolute;
      top: 0;
      bottom: 0;
      left: 0;
      right: 0;
      margin: auto;
      cursor: pointer;
    }

  }

  .our-work__play-stop:hover {
    background-color: $mainColor;
  }

  .our-work__play-stop:hover .play-stop {
    border-color: transparent transparent transparent #ffffff;
  }

  .play-stop {
    width: 0;
    height: 0;
    border-style: solid;
    border-width: 8.5px 0 8.5px 11px;
    border-color: transparent transparent transparent #ffffff;
  }

  .video-play {
    background-color: transparent;
    border-color: transparent transparent transparent transparent;
  }

  .features {
    background-color: #f5f5f5;
    margin: 101px 0 0 0;

    @include max-width-950 {
      margin: 0;
    }

    &__wrapper {
      display: flex;
      flex-wrap: wrap;
      padding: 101px 0 40px 0;

      @include max-width-950 {
        justify-content: center;
      }
    }

    &__item {
      width: 25%;
      background-repeat: no-repeat;
      background-position: 50% 0;
      text-align: center;
      margin: 0 0 56px 0;
      padding: 0 10px;

      @include max-width-950 {
        width: 33.3333%;  
      }

      @include max-width-650 {
        width: 50%;  
      }

      @include max-width-550 {
        width: 100%;  
      }
    }

    &__title {
      display: inline-block;
      font-size: 12px;
      font-weight: bold;
      color: $mainTextColor;
      margin: 67px 0 0 0;
      text-transform: uppercase;
      text-decoration: none;
    }

    &__description {
      font-family: $notoSans;
      font-size: 16px;
      color: $textColor;
      margin: 11px 0 0 0;
      line-height: 24px;
      padding: 0 1px;
    }

  }

  .diamond {
    background-image: url(./assets/images/diamond.png);
  }

  .arc {
    background-image: url(./assets/images/arc.png);
  }

  .phone {
    background-image: url(./assets/images/phone.png);
  }

  .joy {
    background-image: url(./assets/images/joy.png);
  }

  .plane {
    background-image: url(./assets/images/plane.png);
  }

  .star {
    background-image: url(./assets/images/star_2.png);
  }

  .magic-wand {
    background-image: url(./assets/images/magic_wand.png);
  }

  .paint-bucket {
    background-image: url(./assets/images/paint_bucket.png);
  }

</style>