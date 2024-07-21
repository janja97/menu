<template>
  <div class="p-md-5 content">
    <div class="accordion" id="accordionExample">
      <!-- topli napici i kave -->
      <div class="accordion-item">
        <h2 class="accordion-header">
          <button class="accordion-button" type="button" data-bs-toggle="collapse" data-bs-target="#collapseOne" aria-expanded="true" aria-controls="collapseOne">
            Topli napici i kave
          </button>
        </h2>
        <div id="collapseOne" class="accordion-collapse collapse show" data-bs-parent="#accordionExample">
          <div class="cards d-none d-md-flex flex-wrap">
            <div 
              class="card d-flex" 
              v-for="(drink, index) in kaveITopliNapici" 
              :key="index"
            >
              <img :src="drink.image" class="card-img" :alt="drink.name">
              <div class="card-body">
                <h5 class="card-title">{{ drink.name }}</h5>
                <p class="card-text">{{ drink.price }} HRK</p>
              </div>
            </div>
          </div>
          <div class="accordion-body d-md-none">
            <carousel :items-to-show="1">
              <slide v-for="(drink, index) in kaveITopliNapici" :key="index">
                <div class="carousel-body">
                  <div v-if="drink.animationClass1" :class="drink.animationClass1">
                    <img :src="drink.animationImage1" class="kave col-12" :alt="drink.name">
                  </div>
                  <div v-if="drink.animationClass2" :class="drink.animationClass2">
                    <img :src="drink.animationImage2" class="kave col-12" :alt="drink.name">
                  </div>
                  <div class="content-div">
                    <img :src="drink.image" alt="Drink Image" class="carousel-img">
                    <div class="text-center mt-2 pt-2">
                      <h5 class="title">{{ drink.name }}</h5>
                      <p class="price">{{ drink.price }} HRK</p>
                    </div>
                  </div>
                </div>
              </slide>
              <template #addons>
                <pagination />
                <navigation />
              </template>
            </carousel>
          </div>
        </div>
      </div>
      <!-- bezalkoholno -->
      <div class="accordion-item">
        <h2 class="accordion-header">
          <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#collapseTwo" aria-expanded="false" aria-controls="collapseTwo">
            Voda i sokovi
          </button>
        </h2>
        <div id="collapseTwo" class="accordion-collapse collapse" data-bs-parent="#accordionExample">
          <div class="cards d-none d-md-flex flex-wrap">
            <div 
              class="card d-flex" 
              v-for="(drink, index) in bezalkoholnaPica" 
              :key="index"
            >
              <img :src="drink.image" class="card-img" :alt="drink.name">
              <div class="card-body">
                <h5 class="card-title">{{ drink.name }}</h5>
                <p class="card-text">{{ drink.price }} HRK</p>
              </div>
            </div>
          </div>
          <div class="accordion-body d-md-none">
            <carousel :items-to-show="1">
              <slide v-for="(drink, index) in bezalkoholnaPica" :key="index">
                <div class="carousel-body">
                  <div v-if="drink.animationClass1" :class="drink.animationClass1">
                    <img :src="drink.animationImage1" class="kave col-12" :alt="drink.name">
                  </div>
                  <div v-if="drink.animationClass2" :class="drink.animationClass2">
                    <img :src="drink.animationImage2" class="kave col-12" :alt="drink.name">
                  </div>
                  <div class="content-div">
                    <img :src="drink.image" alt="Drink Image" class="carousel-img">
                    <div class="text-center mt-2 pt-2">
                      <h5 class="title">{{ drink.name }}</h5>
                      <p class="price">{{ drink.price }} HRK</p>
                    </div>
                  </div>
                </div>
              </slide>
              <template #addons>
                <pagination />
                <navigation />
              </template>
            </carousel>
          </div>
        </div>
      </div>
      <!-- pive -->
      <div class="accordion-item">
        <h2 class="accordion-header">
          <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#collapseThree" aria-expanded="false" aria-controls="collapseThree">
            Pive
          </button>
        </h2>
        <div id="collapseThree" class="accordion-collapse collapse" data-bs-parent="#accordionExample">
          <div class="cards d-none d-md-flex flex-wrap">
            <div 
              class="card d-flex" 
              v-for="(drink, index) in pive" 
              :key="index"
            >
              <img :src="drink.image" class="card-img" :alt="drink.name">
              <div class="card-body">
                <h5 class="card-title">{{ drink.name }}</h5>
                <p class="card-text">{{ drink.price }} HRK</p>
              </div>
            </div>
          </div>
          <div class="accordion-body d-md-none">
            <carousel :items-to-show="1">
              <slide v-for="(drink, index) in pive" :key="index">
                <div class="carousel-body">
                  <div v-if="drink.animationClass1" :class="drink.animationClass1">
                    <img :src="drink.animationImage1" class="kave col-12" :alt="drink.name">
                  </div>
                  <div v-if="drink.animationClass2" :class="drink.animationClass2">
                    <img :src="drink.animationImage2" class="kave col-12" :alt="drink.name">
                  </div>
                  <div class="content-div">
                    <img :src="drink.image" alt="Drink Image" class="carousel-img">
                    <div class="text-center mt-2 pt-2">
                      <h5 class="title">{{ drink.name }}</h5>
                      <p class="price">{{ drink.price }} HRK</p>
                    </div>
                  </div>
                </div>
              </slide>
              <template #addons>
                <pagination />
                <navigation />
              </template>
            </carousel>
          </div>
        </div>
      </div>
      <!-- Vina -->
      <div class="accordion-item">
        <h2 class="accordion-header">
          <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#collapseFour" aria-expanded="false" aria-controls="collapseFour">
            Vina
          </button>
        </h2>
        <div id="collapseFour" class="accordion-collapse collapse" data-bs-parent="#accordionExample">
          <div class="cards d-none d-md-flex flex-wrap">
            <div 
              class="card d-flex" 
              v-for="(drink, index) in vina" 
              :key="index"
            >
              <img :src="drink.image" class="card-img" :alt="drink.name">
              <div class="card-body">
                <h5 class="card-title">{{ drink.name }}</h5>
                <p class="card-text">{{ drink.price }} HRK</p>
              </div>
            </div>
          </div>
          <div class="accordion-body d-md-none">
            <carousel :items-to-show="1">
              <slide v-for="(drink, index) in vina" :key="index">
                <div class="carousel-body">
                  <div v-if="drink.animationClass1" :class="drink.animationClass1">
                    <img :src="drink.animationImage1" class="kave col-12" :alt="drink.name">
                  </div>
                  <div v-if="drink.animationClass2" :class="drink.animationClass2">
                    <img :src="drink.animationImage2" class="kave col-12" :alt="drink.name">
                  </div>
                  <div class="content-div">
                    <img :src="drink.image" alt="Drink Image" class="carousel-img">
                    <div class="text-center mt-2 pt-2">
                      <h5 class="title">{{ drink.name }}</h5>
                      <p class="price">{{ drink.price }} HRK</p>
                    </div>
                  </div>
                </div>
              </slide>
              <template #addons>
                <pagination />
                <navigation />
              </template>
            </carousel>
          </div>
        </div>
      </div>
      <!-- alkohol -->
      <div class="accordion-item">
        <h2 class="accordion-header">
          <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#collapseFive" aria-expanded="false" aria-controls="collapseFive">
            Kratka alkoholna pića
          </button>
        </h2>
        <div id="collapseFive" class="accordion-collapse collapse" data-bs-parent="#accordionExample">
          <div class="cards d-none d-md-flex flex-wrap">
            <div 
              class="card d-flex" 
              v-for="(drink, index) in alkohol" 
              :key="index"
            >
              <img :src="drink.image" class="card-img" :alt="drink.name">
              <div class="card-body">
                <h5 class="card-title">{{ drink.name }}</h5>
                <p class="card-text">{{ drink.price }} HRK</p>
              </div>
            </div>
          </div>
          <div class="accordion-body d-md-none">
            <carousel :items-to-show="1">
              <slide v-for="(drink, index) in alkohol" :key="index">
                <div class="carousel-body">
                  <div v-if="drink.animationClass1" :class="drink.animationClass1">
                    <img :src="drink.animationImage1" class="kave col-12" :alt="drink.name">
                  </div>
                  <div v-if="drink.animationClass2" :class="drink.animationClass2">
                    <img :src="drink.animationImage2" class="kave col-12" :alt="drink.name">
                  </div>
                  <div class="content-div">
                    <img :src="drink.image" alt="Drink Image" class="carousel-img">
                    <div class="text-center mt-2 pt-2">
                      <h5 class="title">{{ drink.name }}</h5>
                      <p class="price">{{ drink.price }} HRK</p>
                    </div>
                  </div>
                </div>
              </slide>
              <template #addons>
                <pagination />
                <navigation />
              </template>
            </carousel>
          </div>
        </div>
      </div>
      <!-- kokteli -->
      <div class="accordion-item">
        <h2 class="accordion-header">
          <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#collapseSix" aria-expanded="false" aria-controls="collapseSix">
           Kokteli
          </button>
        </h2>
        <div id="collapseSix" class="accordion-collapse collapse" data-bs-parent="#accordionExample">
          <div class="cards d-none d-md-flex flex-wrap">
            <div 
              class="card d-flex" 
              v-for="(drink, index) in kokteli" 
              :key="index"
            >
              <img :src="drink.image" class="card-img" :alt="drink.name">
              <div class="card-body">
                <h5 class="card-title">{{ drink.name }}</h5>
                <p class="card-text">{{ drink.price }} HRK</p>
              </div>
            </div>
          </div>
          <div class="accordion-body d-md-none">
            <carousel :items-to-show="1">
              <slide v-for="(drink, index) in kokteli" :key="index">
                <div class="carousel-body">
                  <div v-if="drink.animationClass1" :class="drink.animationClass1">
                    <img :src="drink.animationImage1" class="kave col-12" :alt="drink.name">
                  </div>
                  <div v-if="drink.animationClass2" :class="drink.animationClass2">
                    <img :src="drink.animationImage2" class="kave col-12" :alt="drink.name">
                  </div>
                  <div class="content-div">
                    <img :src="drink.image" alt="Drink Image" class="carousel-img">
                    <div class="text-center mt-2 pt-2">
                      <h5 class="title">{{ drink.name }}</h5>
                      <p class="price">{{ drink.price }} HRK</p>
                    </div>
                  </div>
                </div>
              </slide>
              <template #addons>
                <pagination />
                <navigation />
              </template>
            </carousel>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>


<script setup>
import 'vue3-carousel/dist/carousel.css'
import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel'

// Definiramo kategorije pića i njihova pića
const kaveITopliNapici = [
  {
    name: 'Exspreso',
    image: '/drink/expreso.png',
    price: 10,
    class: 'kava',
    animationClass1: 'animation-div1',
    animationClass2: 'animation-div2',
    animationImage1: '/drink/kava2.png',
    animationImage2: '/drink/kava3.png',
  },
  {
    name: 'Kava',
    image: '/drink/caffe.png',
    price: 10,
    class: 'kava',
    animationClass1: 'animation-div1',
    animationClass2: 'animation-div2',
    animationImage1: '/drink/kava2.png',
    animationImage2: '/drink/kava3.png',
  },
  {
    name: 'Cappuccino',
    image: '/drink/capucino.png',
    price: 12,
    class: 'kava',
    animationClass1: 'animation-div1',
    animationClass2: 'animation-div2',
    animationImage1: '/drink/kava2.png',
    animationImage2: '/drink/kava3.png',
  },
  {
    name: 'Latte',
    image: '/drink/late.png',
    price: 14,
    class: 'kava',
    animationClass1: 'animation-div1',
    animationClass2: 'animation-div2',
    animationImage1: '/drink/kava2.png',
    animationImage2: '/drink/kava3.png',
  },
  {
    name: 'IceCaffe',
    image: '/drink/icecaffe.png',
    price: 14,
    class: 'ice',
    animationClass1: 'animation-div1',
    animationClass2: 'animation-div2',
    animationImage1: '/drink/kava2.png',
    animationImage2: '/drink/ice.png',
  },
  {
    name: 'Čaj',
    image: '/drink/tea.png',
    price: 8,
    class: 'tea',
    animationClass1: 'animation-div1',
    animationClass2: 'animation-div2',
    animationImage1: '/drink/tea1.png',
    animationImage2: '/drink/tea1.png',
  },
];

const bezalkoholnaPica = [
  {
    name: 'Voda',
    image: '/bezalkoholni/vode.png',
    price: 8,
    class: 'water',
  },
  {
    name: 'Voda s okusom',
    image: '/bezalkoholni/vodaSOkusom.png',
    price: 8,
    class: 'water',
  },
  {
    name: 'Mineralna voda',
    image: '/bezalkoholni/mineralna.png',
    price: 8,
    class: 'water',
  },
  {
    name: 'Prirodni sokovi',
    image: '/bezalkoholni/vocni.png',
    price: 12,
    class: 'juice',
    animationClass1: 'animation-div1',
    animationClass2: 'animation-div2',
    animationImage1: '/drink/orange1.png',
    animationImage2: '/drink/orange2.png',
  },
  {
    name: 'Svježe cijedeni sokovi sokovi',
    image: '/bezalkoholni/cjedeni.png',
    price: 12,
    class: 'juice',
    animationClass1: 'animation-div1',
    animationClass2: 'animation-div2',
    animationImage1: '/drink/orange1.png',
    animationImage2: '/drink/orange2.png',
  },
  {
    name: 'Gazirani sokovi',
    image: '/bezalkoholni/gazirani.png',
    price: 12,
    class: 'juice',
  },
  // Dodajte ostala bezalkoholna pića ovde...
];

const pive = [
  {
    name: 'Karlovačko',
    image: '/pivo/karlovacko.png',
    price: 15,
    class: 'beer',
    animationClass1: 'animation-div1',
    animationClass2: 'animation-div2',
    animationImage1: '/pivo/psenica1.png',
    animationImage2: '/pivo/psenica2.png',
  },
  {
    name: 'Ožujsko',
    image: '/pivo/ozujsko.png',
    price: 15,
    class: 'beer',
    animationClass1: 'animation-div1',
    animationClass2: 'animation-div2',
    animationImage1: '/pivo/psenica1.png',
    animationImage2: '/pivo/psenica2.png',
  },
  {
    name: 'Heineken',
    image: '/pivo/heinken.png',
    price: 18,
    class: 'beer',
    animationClass1: 'animation-div1',
    animationClass2: 'animation-div2',
    animationImage1: '/pivo/psenica1.png',
    animationImage2: '/pivo/psenica2.png',
  },
  {
    name: 'Paulaner',
    image: '/pivo/paul.png',
    price: 20,
    class: 'beer',
    animationClass1: 'animation-div1',
    animationClass2: 'animation-div2',
    animationImage1: '/pivo/psenica1.png',
    animationImage2: '/pivo/psenica2.png',
  },
  {
    name: 'Guinness',
    image: '/pivo/guinniess.png',
    price: 22,
    class: 'beer',
    animationClass1: 'animation-div1',
    animationClass2: 'animation-div2',
    animationImage1: '/pivo/psenica1.png',
    animationImage2: '/pivo/psenica2.png',
  },
  {
    name: 'Corona',
    image: '/pivo/corona.png',
    price: 20,
    class: 'beer',
    animationClass1: 'animation-div1',
    animationClass2: 'animation-div2',
    animationImage1: '/pivo/psenica1.png',
    animationImage2: '/pivo/psenica2.png',
  },
  {
    name: 'Stella Artois',
    image: '/pivo/steča.png',
    price: 18,
    class: 'beer',
    animationClass1: 'animation-div1',
    animationClass2: 'animation-div2',
    animationImage1: '/pivo/psenica1.png',
    animationImage2: '/pivo/psenica2.png',
  },
  {
    name: 'Točeno pivo 0.3L',
    image: '/pivo/toceno1.png',
    price: 12,
    class: 'beer',
    animationClass1: 'animation-div1',
    animationClass2: 'animation-div2',
    animationImage1: '/pivo/psenica1.png',
    animationImage2: '/pivo/psenica2.png',
  },
  {
    name: 'Točeno pivo 0.5L',
    image: '/pivo/toceno2.png',
    price: 18,
    class: 'beer',
    animationClass1: 'animation-div1',
    animationClass2: 'animation-div2',
    animationImage1: '/pivo/psenica1.png',
    animationImage2: '/pivo/psenica2.png',
  },
  // Dodajte ostala piva ovde...
];

const vina = [
  {
    name: 'Dingač',
    image: '/vino/dingač.png',
    price: 30, // Po deci
    class: 'wine',
    animationClass1: 'animation-div1',
    animationClass2: 'animation-div2',
    animationImage1: '/drink/dingac1.png',
    animationImage2: '/drink/dingac2.png',
  },
  {
    name: 'Plavac Mali',
    image: '/vino/plavac.png',
    price: 25, // Po deci
    class: 'wine',
    animationClass1: 'animation-div1',
    animationClass2: 'animation-div2',
    animationImage1: '/drink/plavac1.png',
    animationImage2: '/drink/plavac2.png',
  },
  {
    name: 'Vranac',
    image: '/vino/vranac.png',
    price: 20, // Po deci
    class: 'wine',
    animationClass1: 'animation-div1',
    animationClass2: 'animation-div2',
    animationImage1: '/drink/vranac1.png',
    animationImage2: '/drink/vranac2.png',
  },
  {
    name: 'Graševina',
    image: '/vino/grasevina.png',
    price: 15, // Po deci
    class: 'wine',
    animationClass1: 'animation-div1',
    animationClass2: 'animation-div2',
    animationImage1: '/drink/grasevina1.png',
    animationImage2: '/drink/grasevina2.png',
  },
  {
    name: 'Domaće bijelo vino 0.2L',
    image: '/vino/bijelo.png',
    price: 10,
    class: 'wine',
    animationClass1: 'animation-div1',
    animationClass2: 'animation-div2',
    animationImage1: '/drink/bijelo1.png',
    animationImage2: '/drink/bijelo2.png',
  },
  {
    name: 'Domaće crno vino 0.2L',
    image: '/vino/crno.png',
    price: 10,
    class: 'wine',
    animationClass1: 'animation-div1',
    animationClass2: 'animation-div2',
    animationImage1: '/drink/crno1.png',
    animationImage2: '/drink/crno2.png',
  },
  {
    name: 'Rose',
    image: '/vino/rose.png',
    price: 20,
    class: 'wine',
    animationClass1: 'animation-div1',
    animationClass2: 'animation-div2',
    animationImage1: '/drink/rose1.png',
    animationImage2: '/drink/rose2.png',
  },
  // Dodajte ostala vina ovde...
];
const alkohol = [
  {
    name: 'Šljivovica',
    image: '/drink/sljivovica.png',
    price: 20,
    class: 'rakija',
    animationClass1: 'animation-div1',
    animationClass2: 'animation-div2',
    animationImage1: '/drink/sljivovica1.png',
    animationImage2: '/drink/sljivovica2.png',
  },
  {
    name: 'Lozovača',
    image: '/drink/lozovaca.png',
    price: 20,
    class: 'rakija',
    animationClass1: 'animation-div1',
    animationClass2: 'animation-div2',
    animationImage1: '/drink/lozovaca1.png',
    animationImage2: '/drink/lozovaca2.png',
  },
  {
    name: 'Medovača',
    image: '/drink/medovaca.png',
    price: 25,
    class: 'rakija',
    animationClass1: 'animation-div1',
    animationClass2: 'animation-div2',
    animationImage1: '/drink/medovaca1.png',
    animationImage2: '/drink/medovaca2.png',
  },
  {
    name: 'Viljamovka',
    image: '/drink/viljamovka.png',
    price: 25,
    class: 'rakija',
    animationClass1: 'animation-div1',
    animationClass2: 'animation-div2',
    animationImage1: '/drink/viljamovka1.png',
    animationImage2: '/drink/viljamovka2.png',
  },
  {
    name: 'Vinjak',
    image: '/drink/vinjak.png',
    price: 30,
    class: 'vinjak',
    animationClass1: 'animation-div1',
    animationClass2: 'animation-div2',
    animationImage1: '/drink/vinjak1.png',
    animationImage2: '/drink/vinjak2.png',
  },
  {
    name: 'Konjak',
    image: '/drink/konjak.png',
    price: 35,
    class: 'konjak',
    animationClass1: 'animation-div1',
    animationClass2: 'animation-div2',
    animationImage1: '/drink/konjak1.png',
    animationImage2: '/drink/konjak2.png',
  },
  {
    name: 'Likeri - Amaretto',
    image: '/drink/amaretto.png',
    price: 25,
    class: 'liker',
    animationClass1: 'animation-div1',
    animationClass2: 'animation-div2',
    animationImage1: '/drink/amaretto1.png',
    animationImage2: '/drink/amaretto2.png',
  },
  {
    name: 'Likeri - Baileys',
    image: '/drink/baileys.png',
    price: 25,
    class: 'liker',
    animationClass1: 'animation-div1',
    animationClass2: 'animation-div2',
    animationImage1: '/drink/baileys1.png',
    animationImage2: '/drink/baileys2.png',
  },
  {
    name: 'Likeri - Jägermeister',
    image: '/drink/jagermeister.png',
    price: 25,
    class: 'liker',
    animationClass1: 'animation-div1',
    animationClass2: 'animation-div2',
    animationImage1: '/drink/jagermeister1.png',
    animationImage2: '/drink/jagermeister2.png',
  },
  {
    name: 'Likeri - Grand Marnier',
    image: '/drink/grandmarnier.png',
    price: 30,
    class: 'liker',
    animationClass1: 'animation-div1',
    animationClass2: 'animation-div2',
    animationImage1: '/drink/grandmarnier1.png',
    animationImage2: '/drink/grandmarnier2.png',
  },
    
];
const kokteli = [
    {
      name: 'Margarita',
      image: '/kokteli/margarita.png',
      price: 35,
      class: 'cocktail',
      animationClass1: 'animation-div1',
      animationClass2: 'animation-div2',
      animationImage1: '/drink/margarita1.png',
      animationImage2: '/drink/margarita2.png',
    },
    {
      name: 'Mojito',
      image: '/kokteli/mojito.png',
      price: 30,
      class: 'cocktail',
      animationClass1: 'animation-div1',
      animationClass2: 'animation-div2',
      animationImage1: '/drink/mojito1.png',
      animationImage2: '/drink/mojito2.png',
    },
    {
      name: 'Pina Colada',
      image: '/kokteli/pina.png',
      price: 35,
      class: 'cocktail',
      animationClass1: 'animation-div1',
      animationClass2: 'animation-div2',
      animationImage1: '/drink/pinacolada1.png',
      animationImage2: '/drink/pinacolada2.png',
    },
    {
      name: 'Daiquiri',
      image: '/kokteli/daiquiri.png',
      price: 32,
      class: 'cocktail',
      animationClass1: 'animation-div1',
      animationClass2: 'animation-div2',
      animationImage1: '/drink/daiquiri1.png',
      animationImage2: '/drink/daiquiri2.png',
    },
    {
      name: 'Tequila Sunrise',
      image: '/kokteli/sunrise.png',
      price: 34,
      class: 'cocktail',
      animationClass1: 'animation-div1',
      animationClass2: 'animation-div2',
      animationImage1: '/drink/tequilasunrise1.png',
      animationImage2: '/drink/tequilasunrise2.png',
    },
    {
      name: 'Cosmopolitan',
      image: '/kokteli/cosmo.png',
      price: 33,
      class: 'cocktail',
      animationClass1: 'animation-div1',
      animationClass2: 'animation-div2',
      animationImage1: '/drink/cosmopolitan1.png',
      animationImage2: '/drink/cosmopolitan2.png',
    },
    {
      name: 'Mai Tai',
      image: '/kokteli/mai.png',
      price: 36,
      class: 'cocktail',
      animationClass1: 'animation-div1',
      animationClass2: 'animation-div2',
      animationImage1: '/drink/maitai1.png',
      animationImage2: '/drink/maitai2.png',
    },
    {
      name: 'Bloody Mary',
      image: '/kokteli/mary.png',
      price: 32,
      class: 'cocktail',
      animationClass1: 'animation-div1',
      animationClass2: 'animation-div2',
      animationImage1: '/drink/bloodymary1.png',
      animationImage2: '/drink/bloodymary2.png',
    },
    {
      name: 'Martini',
      image: '/kokteli/martini.png',
      price: 35,
      class: 'cocktail',
      animationClass1: 'animation-div1',
      animationClass2: 'animation-div2',
      animationImage1: '/drink/martini1.png',
      animationImage2: '/drink/martini2.png',
    },
    {
      name: 'Gin Tonic',
      image: '/kokteli/tonic.png',
      price: 30,
      class: 'cocktail',
      animationClass1: 'animation-div1',
      animationClass2: 'animation-div2',
      animationImage1: '/drink/gintonic1.png',
      animationImage2: '/drink/gintonic2.png',
    },
    {
      name: 'Long Island Iced Tea',
      image: '/kokteli/long.png',
      price: 38,
      class: 'cocktail',
      animationClass1: 'animation-div1',
      animationClass2: 'animation-div2',
      animationImage1: '/drink/longisland1.png',
      animationImage2: '/drink/longisland2.png',
    },
    {
      name: 'Sex on the Beach',
      image: '/kokteli/sex.png',
      price: 36,
      class: 'cocktail',
      animationClass1: 'animation-div1',
      animationClass2: 'animation-div2',
      animationImage1: '/drink/sexonthebeach1.png',
      animationImage2: '/drink/sexonthebeach2.png',
    },
    {
      name: 'Old Fashioned',
      image: '/kokteli/old.png',
      price: 35,
      class: 'cocktail',
      animationClass1: 'animation-div1',
      animationClass2: 'animation-div2',
      animationImage1: '/drink/oldfashioned1.png',
      animationImage2: '/drink/oldfashioned2.png',
    },
]
</script>



<style scoped>
/* acordion */
.accordion-item {
  background-color: transparent;
  border: none;
}

.accordion-button {
  background-color: transparent !important;
  color: #3C2C32 !important;
  border: none !important;
  font-weight: 700;
  font-size: 18px;
  padding: 20px 20px;
}
.accordion-button::after {
  display: none;
}

.accordion-button:focus {
  box-shadow: none; /* Remove focus box-shadow */
}
/* card */

.cards {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
  justify-content: center;

}

.card {
  width: 13rem;
  border: none;
  background: transparent;
  color: #3C2C32;
}

.card-img {
  width: 100%;
  height: auto;
  object-fit: cover;
}

.card-body {
  text-align: center;
}

/* slider / carouesl  */
.carousel-body {
  color: #3C2C32;

}
.carousel-img {
 height: 200px;
 width: auto;
  z-index: 99;
}
.content-div {
  position: relative;
}

.title {
  font-weight: 700;
}
.price {
  font-weight: 900;
  color: #F9AD59;
  font-size: 20px;
}
.animation-div1 {
  position: relative;
  width: 90vw; 
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  justify-content: space-between;
  animation: rotate-90-right-ccw  25s linear infinite;
  top: 150px;
}
.animation-div2 {
  position: relative;
  width: 90vw; 
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  justify-content: space-between;
  animation: rotate-90-right-ccw2  25s linear infinite;
  top: 150px;
}

@keyframes rotate-90-right-ccw {
  0% {
    transform: rotate(0deg);
  }
  50% {
    transform: rotate(200deg);
  }
  100% {
    transform: rotate(0deg);
  }
}
@keyframes rotate-90-right-ccw2 {
  0% {
    transform: rotate(200deg);
  }
  50% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(200deg);
  }
}
.kave {
  width: 150px;
  height: auto;
}
/* .content-div {
  position: relative;
  top: 50px;
  left: 50px;
} */
/* .kava {
  content: url('./drink/kava1.png');
  width: 100px;
  position: absolute;

} */

/* ----------------------------------------------
 * Generated by Animista on 2024-7-17 13:25:3
 * Licensed under FreeBSD License.
 * See http://animista.net/license for more info. 
 * w: http://animista.net, t: @cssanimista
 * ---------------------------------------------- */

/**
 * ----------------------------------------
 * animation rotate-90-right-ccw
 * ----------------------------------------
 */
 /* @-webkit-keyframes rotate-90-right-ccw {
  0% {
    -webkit-transform: rotate(0);
            transform: rotate(0);
    -webkit-transform-origin: right;
            transform-origin: right;
  }
  100% {
    -webkit-transform: rotate(-180deg);
            transform: rotate(-180deg);
    -webkit-transform-origin: right;
            transform-origin: right;
  }
}
@keyframes rotate-90-right-ccw {
  0% {
    -webkit-transform: rotate(0);
            transform: rotate(0);
    -webkit-transform-origin: right;
            transform-origin: right;
  }
  100% {
    -webkit-transform: rotate(-180deg);
            transform: rotate(-180deg);
    -webkit-transform-origin: right;
            transform-origin: right;
  }
} */

/* @keyframes moveCoffee {
  0% {
    transform: translateX(0%) translateY(50px);
  }
  50% {
    transform: translateX(80vw) translateY(50px);
  }
  100% {
    transform: translateX(0%) translateY(50px);
  }
} */

</style>
