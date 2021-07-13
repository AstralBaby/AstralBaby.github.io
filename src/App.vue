<template>
  <div id="app" class="">
    <div class="h-full relative flex">
      <div id="particles" class="welcome">
      </div>
        <div class="h-1/2 self-center w-full flex justify-center text-center items-center text-white flex-col">
          <div class="name font-weight-bold mb-3 lg:mb-0">Catalina Fernandez</div>
          <div class="subtitle font-light">Frontend Engineer</div>
        </div>
    </div>
    <div class="bg-white min-h-1/2 pb-20 lg:px-10 px-3">
      <div class="">
        <div class="text-3xl text-gray-700 font-bold block text-center">About me</div>
      </div>
      <div class="lg:flex w-full lg:w-1/2 mx-auto py-10">
        <div class="lg:w-1/4">
          <img src="@/assets/pfp_background.svg" class="object-top object-cover rounded-full mx-auto" alt="">
        </div>
        <div class="lg:w-3/4 px-10">
        <div class="flex">
          <i class='bx bxs-quote-alt-left lg:text-5xl text-indigo-600'></i>
          <div class="flex-grow text-gray-500 leading-7 px-5 mt-5">
            My name is <b>Catalina Fernandez</b>, i am 18 years old, i live in Argentina, sadly i have no cats;
            Im a Software Developer and a passionate UI Designer.
            I have been interested in software since im 12 years old and i've been working as a Software Developer since 16.
            I feel connected and inspired by computers, i love what i do and i love to full dedicate myself to my job.
          </div>
          <i class='bx bxs-quote-alt-right lg:text-5xl self-end text-purple-600'></i>
        </div>
        </div>
      </div>
    </div>
    <div class="bg-white w-full lg:min-h-1/2 px-10">
      <div class="text-3xl text-gray-700 font-bold flex-grow text-center">Portfolio</div>
      <div class="text-gray-500 text-lg text-center">
        <div class="py-3">In this section you'll find some of my crafts.</div>
      </div>
      <div class="">
        <carousel :per-page="1" class="mx-auto lg:w-3/4 w-full" loop>
          <slide v-for="(image, index) in gallery" :key='index' class="bg-white p-1 shadow-lg rounded-xl">
            <img :src="image" alt="Novuum login page">
          </slide>
        </carousel>
      </div>
    </div>
  </div>
</template>

<script>
import '@/assets/css.css'
import 'particles.js'
import particlesConfig from '@/assets/particles.config.json'
import { Carousel, Slide } from 'vue-carousel';

export default {
  name: 'App',
  components: {
    Carousel, Slide
  },
  data: () => ({
    gallery: [
      require('@/assets/designs/nv/login.png'),
      require('@/assets/designs/nv/home.png'),
      require('@/assets/designs/nv/chat.png'),
      require('@/assets/designs/nv/calendar.png'),

    ]
  }),
  mounted() {
    if (!window.particlesJS) return false

    window.particlesJS("particles", particlesConfig, function(){
    })

    document.title = "Frontend Engineer - Catalina Fernandez"
  }
}
</script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Pacifico&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100;0,200;0,300;0,500;0,600;0,700;1,100;1,200;1,300&display=swap');
@import url('https://unpkg.com/boxicons@2.0.7/css/boxicons.min.css');

@media (min-width: 1024px) {
  .name {
    font-size: 100px;
    font-weight: 500;
  }
  
  .subtitle {
    font-size: 30px;
  }

}

.subtitle {
  font-size: 25px;
}
.name {
  font-family: 'Pacifico', cursive;
  font-size: 70px;
  font-weight: 500;
  line-height: .9;
}
.welcome {
  background-image: url('~@/assets/wave.svg');
  background-position: center;
  background-position-y: 20vh;
  background-size: cover;
  background-repeat: no-repeat;
}
</style>
