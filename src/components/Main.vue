<template>
  <div class="p-md-5 content">
    <div class="accordion" id="accordionExample">
      <div 
        class="accordion-item" 
        v-for="(category, catIndex) in drinkCategories" 
        :key="catIndex"
      >
        <h2 class="accordion-header">
          <button 
            class="accordion-button" 
            type="button" 
            :data-bs-toggle="'collapse'" 
            :data-bs-target="'#collapse' + catIndex" 
            :aria-expanded="catIndex === 0 ? 'true' : 'false'" 
            :aria-controls="'collapse' + catIndex"
          >
            {{ category.name }}
          </button>
        </h2>
        <div 
          :id="'collapse' + catIndex" 
          class="accordion-collapse collapse" 
          :class="{ show: catIndex === 0 }" 
          data-bs-parent="#accordionExample"
        >
          <div class="cards d-none d-md-flex flex-wrap">
            <div 
              class="card d-flex" 
              v-for="(drink, index) in category.drinks" 
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
              <slide v-for="(drink, index) in category.drinks" :key="index">
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
const drinkCategories = [
  {
    name: 'Kave i Topli napici',
    drinks: [
      {
        name: 'Exspreso',
        image: '../public/drink/expreso.png',
        price: 10,
        class: 'kava',
        animationClass1: 'animation-div1',
        animationClass2: 'animation-div2',
        animationImage1: '/public/drink/kava2.png',
        animationImage2: '/public/drink/kava3.png',
      },
      {
        name: 'Kava',
        image: '../public/drink/caffe.png',
        price: 10,
        class: 'kava',
        animationClass1: 'animation-div1',
        animationClass2: 'animation-div2',
        animationImage1: '/public/drink/kava2.png',
        animationImage2: '/public/drink/kava3.png',
      },
      {
        name: 'Cappuccino',
        image: '../public/drink/capucino.png',
        price: 12,
        class: 'kava',
        animationClass1: 'animation-div1',
        animationClass2: 'animation-div2',
        animationImage1: '/public/drink/kava2.png',
        animationImage2: '/public/drink/kava3.png',
      },
      {
        name: 'Latte',
        image: '../public/drink/late.png',
        price: 14,
        class: 'kava',
        animationClass1: 'animation-div1',
        animationClass2: 'animation-div2',
        animationImage1: '/public/drink/kava2.png',
        animationImage2: '/public/drink/kava3.png',
      },
      {
        name: 'IceCaffe',
        image: '../public/drink/icecaffe.png',
        price: 14,
        class: 'ice',
        animationClass1: 'animation-div1',
        animationClass2: 'animation-div2',
        animationImage1: '/public/drink/kava2.png',
        animationImage2: '/public/drink/ice.png',
      },
      {
        name: 'Čaj',
        image: '../public/drink/tea.png',
        price: 8,
        class: 'tea',
        animationClass1: 'animation-div1',
        animationClass2: 'animation-div2',
        animationImage1: '/public/drink/tea1.png',
        animationImage2: '/public/drink/tea1.png',
      },
    ],
  },
  {
    name: 'Bezalkoholna pića',
    drinks: [
      {
        name: 'Voda',
        image: './public/bezalkoholni/vode.png',
        price: 8,
        class: 'water',
       
      },
      {
        name: 'Voda s okusom',
        image: './public/bezalkoholni/vodaSOkusom.png',
        price: 8,
        class: 'water',
       
      },
      {
        name: 'Mineralna voda',
        image: './public/bezalkoholni/mineralna.png',
        price: 8,
        class: 'water',
     
      },
      {
        name: 'Prirodni sokovi',
        image: './public/bezalkoholni/vocni.png',
        price: 12,
        class: 'juice',
        animationClass1: 'animation-div1',
        animationClass2: 'animation-div2',
        animationImage1: '/public/drink/orange1.png',
        animationImage2: '/public/drink/orange2.png',
      },
      {
        name: 'Svježe cijedeni sokovi sokovi',
        image: './public/bezalkoholni/cjedeni.png',
        price: 12,
        class: 'juice',
        animationClass1: 'animation-div1',
        animationClass2: 'animation-div2',
        animationImage1: '/public/drink/orange1.png',
        animationImage2: '/public/drink/orange2.png',
      },
      {
        name: 'Gazirani sokovi',
        image: './public/bezalkoholni/gazirani.png',
        price: 12,
        class: 'juice',
    
      },

      // Dodajte ostala bezalkoholna pića ovde...
    ],
  },
  {
    name: 'Pive',
    drinks: [
      {
        name: 'Karlovačko',
        image: './public/pivo/karlovacko.png',
        price: 15,
        class: 'beer',
  
      },
      {
        name: 'Ožujsko',
        image: './public/pivo/ozujsko.png',
        price: 15,
        class: 'beer',
    
      },
      {
        name: 'Heineken',
        image: './public/pivo/heinken.png',
        price: 18,
        class: 'beer',

      },
      {
        name: 'Paulaner',
        image: './public/pivo/paul.png',
        price: 20,
        class: 'beer',
      },
      {
        name: 'Guinness',
        image: './public/pivo/guinniess.png',
        price: 22,
        class: 'beer',
      },
      {
        name: 'Corona',
        image: './public/pivo/corona.png',
        price: 20,
        class: 'beer',
      },
      {
        name: 'Stella Artois',
        image: './public/pivo/steča.png',
        price: 18,
        class: 'beer',
      },
      {
        name: 'Točeno pivo 0.3L',
        image: './public/pivo/toceno1.png',
        price: 12,
        class: 'beer',
      },
      {
        name: 'Točeno pivo 0.5L',
        image: './public/pivo/toceno2.png',
        price: 18,
        class: 'beer',
      },
      // Dodajte ostala alkoholna pića ovde...
    ],
  },
  {
    name: 'Vina',
    drinks: [
      {
        name: 'Dingač',
        image: './public/vino/dingac.png',
        price: 30, // Po deci
        class: 'wine',
        animationClass1: 'animation-div1',
        animationClass2: 'animation-div2',
        animationImage1: '/public/drink/dingac1.png',
        animationImage2: '/public/drink/dingac2.png',
      },
      {
        name: 'Plavac Mali',
        image: './public/vino/plavac.png',
        price: 25, // Po deci
        class: 'wine',
        animationClass1: 'animation-div1',
        animationClass2: 'animation-div2',
        animationImage1: '/public/drink/plavac1.png',
        animationImage2: '/public/drink/plavac2.png',
      },
      {
        name: 'Vranac',
        image: './public/vino/vranac.png',
        price: 20, // Po deci
        class: 'wine',
        animationClass1: 'animation-div1',
        animationClass2: 'animation-div2',
        animationImage1: '/public/drink/vranac1.png',
        animationImage2: '/public/drink/vranac2.png',
      },
      {
        name: 'Graševina',
        image: './public/vino/grasevina.png',
        price: 15, // Po deci
        class: 'wine',
        animationClass1: 'animation-div1',
        animationClass2: 'animation-div2',
        animationImage1: '/public/drink/grasevina1.png',
        animationImage2: '/public/drink/grasevina2.png',
      },
      {
        name: 'Domaće bijelo vino 0.2L',
        image: './public/vino/bijelo.png',
        price: 10, // Po deci
        class: 'wine',
        animationClass1: 'animation-div1',
        animationClass2: 'animation-div2',
        animationImage1: '/public/drink/domace-bijelo1.png',
        animationImage2: '/public/drink/domace-bijelo2.png',
      },
      {
        name: 'Domaće bijelo vino 1L',
        image: './public/vino/bijelo.png',
        price: 70, // Po litri
        class: 'wine',
        animationClass1: 'animation-div1',
        animationClass2: 'animation-div2',
        animationImage1: '/public/drink/domace-bijelo1.png',
        animationImage2: '/public/drink/domace-bijelo2.png',
      },
      {
        name: 'Domaće crno vino 0.2L',
        image: './public/vino/crno.png',
        price: 10, // Po deci
        class: 'wine',
        animationClass1: 'animation-div1',
        animationClass2: 'animation-div2',
        animationImage1: '/public/drink/domace-crno1.png',
        animationImage2: '/public/drink/domace-crno2.png',
      },
      {
        name: 'Domaće crno vino 1L',
        image: './public/vinno/crno.png',
        price: 70, // Po litri
        class: 'wine',
        animationClass1: 'animation-div1',
        animationClass2: 'animation-div2',
        animationImage1: '/public/drink/domace-crno1.png',
        animationImage2: '/public/drink/domace-crno2.png',
      },
    ],
  },
  {
    name: 'Alkoholna pića',
    drinks: [
      {
        name: 'Šljivovica',
        image: './public/drink/sljivovica.png',
        price: 20,
        class: 'rakija',
        animationClass1: 'animation-div1',
        animationClass2: 'animation-div2',
        animationImage1: '/public/drink/sljivovica1.png',
        animationImage2: '/public/drink/sljivovica2.png',
      },
      {
        name: 'Lozovača',
        image: './public/drink/lozovaca.png',
        price: 20,
        class: 'rakija',
        animationClass1: 'animation-div1',
        animationClass2: 'animation-div2',
        animationImage1: '/public/drink/lozovaca1.png',
        animationImage2: '/public/drink/lozovaca2.png',
      },
      {
        name: 'Medovača',
        image: './public/drink/medovaca.png',
        price: 25,
        class: 'rakija',
        animationClass1: 'animation-div1',
        animationClass2: 'animation-div2',
        animationImage1: '/public/drink/medovaca1.png',
        animationImage2: '/public/drink/medovaca2.png',
      },
      {
        name: 'Viljamovka',
        image: './public/drink/viljamovka.png',
        price: 25,
        class: 'rakija',
        animationClass1: 'animation-div1',
        animationClass2: 'animation-div2',
        animationImage1: '/public/drink/viljamovka1.png',
        animationImage2: '/public/drink/viljamovka2.png',
      },
      {
        name: 'Vinjak',
        image: './public/drink/vinjak.png',
        price: 30,
        class: 'vinjak',
        animationClass1: 'animation-div1',
        animationClass2: 'animation-div2',
        animationImage1: '/public/drink/vinjak1.png',
        animationImage2: '/public/drink/vinjak2.png',
      },
      {
        name: 'Konjak',
        image: './public/drink/konjak.png',
        price: 35,
        class: 'konjak',
        animationClass1: 'animation-div1',
        animationClass2: 'animation-div2',
        animationImage1: '/public/drink/konjak1.png',
        animationImage2: '/public/drink/konjak2.png',
      },
      {
        name: 'Likeri - Amaretto',
        image: './public/drink/amaretto.png',
        price: 25,
        class: 'liker',
        animationClass1: 'animation-div1',
        animationClass2: 'animation-div2',
        animationImage1: '/public/drink/amaretto1.png',
        animationImage2: '/public/drink/amaretto2.png',
      },
      {
        name: 'Likeri - Baileys',
        image: './public/drink/baileys.png',
        price: 25,
        class: 'liker',
        animationClass1: 'animation-div1',
        animationClass2: 'animation-div2',
        animationImage1: '/public/drink/baileys1.png',
        animationImage2: '/public/drink/baileys2.png',
      },
      {
        name: 'Likeri - Jägermeister',
        image: './public/drink/jagermeister.png',
        price: 25,
        class: 'liker',
        animationClass1: 'animation-div1',
        animationClass2: 'animation-div2',
        animationImage1: '/public/drink/jagermeister1.png',
        animationImage2: '/public/drink/jagermeister2.png',
      },
      {
        name: 'Likeri - Grand Marnier',
        image: './public/drink/grandmarnier.png',
        price: 30,
        class: 'liker',
        animationClass1: 'animation-div1',
        animationClass2: 'animation-div2',
        animationImage1: '/public/drink/grandmarnier1.png',
        animationImage2: '/public/drink/grandmarnier2.png',
      },
    ],
  },
  {
    name: 'Kokteli',
    drinks: [
      {
        name: 'Margarita',
        image: './public/kokteli/margarita.png',
        price: 35,
        class: 'cocktail',
        animationClass1: 'animation-div1',
        animationClass2: 'animation-div2',
        animationImage1: '/public/drink/margarita1.png',
        animationImage2: '/public/drink/margarita2.png',
      },
      {
        name: 'Mojito',
        image: './public/kokteli/mojito.png',
        price: 30,
        class: 'cocktail',
        animationClass1: 'animation-div1',
        animationClass2: 'animation-div2',
        animationImage1: '/public/drink/mojito1.png',
        animationImage2: '/public/drink/mojito2.png',
      },
      {
        name: 'Pina Colada',
        image: './public/kokteli/pina.png',
        price: 35,
        class: 'cocktail',
        animationClass1: 'animation-div1',
        animationClass2: 'animation-div2',
        animationImage1: '/public/drink/pinacolada1.png',
        animationImage2: '/public/drink/pinacolada2.png',
      },
      {
        name: 'Daiquiri',
        image: './public/kokteli/daiquiri.png',
        price: 32,
        class: 'cocktail',
        animationClass1: 'animation-div1',
        animationClass2: 'animation-div2',
        animationImage1: '/public/drink/daiquiri1.png',
        animationImage2: '/public/drink/daiquiri2.png',
      },
      {
        name: 'Tequila Sunrise',
        image: './public/kokteli/sunrise.png',
        price: 34,
        class: 'cocktail',
        animationClass1: 'animation-div1',
        animationClass2: 'animation-div2',
        animationImage1: '/public/drink/tequilasunrise1.png',
        animationImage2: '/public/drink/tequilasunrise2.png',
      },
      {
        name: 'Cosmopolitan',
        image: './public/kokteli/cosmo.png',
        price: 33,
        class: 'cocktail',
        animationClass1: 'animation-div1',
        animationClass2: 'animation-div2',
        animationImage1: '/public/drink/cosmopolitan1.png',
        animationImage2: '/public/drink/cosmopolitan2.png',
      },
      {
        name: 'Mai Tai',
        image: './public/kokteli/mai.png',
        price: 36,
        class: 'cocktail',
        animationClass1: 'animation-div1',
        animationClass2: 'animation-div2',
        animationImage1: '/public/drink/maitai1.png',
        animationImage2: '/public/drink/maitai2.png',
      },
      {
        name: 'Bloody Mary',
        image: './public/kokteli/mary.png',
        price: 32,
        class: 'cocktail',
        animationClass1: 'animation-div1',
        animationClass2: 'animation-div2',
        animationImage1: '/public/drink/bloodymary1.png',
        animationImage2: '/public/drink/bloodymary2.png',
      },
      {
        name: 'Martini',
        image: './public/kokteli/martini.png',
        price: 35,
        class: 'cocktail',
        animationClass1: 'animation-div1',
        animationClass2: 'animation-div2',
        animationImage1: '/public/drink/martini1.png',
        animationImage2: '/public/drink/martini2.png',
      },
      {
        name: 'Gin Tonic',
        image: './public/kokteli/tonic.png',
        price: 30,
        class: 'cocktail',
        animationClass1: 'animation-div1',
        animationClass2: 'animation-div2',
        animationImage1: '/public/drink/gintonic1.png',
        animationImage2: '/public/drink/gintonic2.png',
      },
      {
        name: 'Long Island Iced Tea',
        image: './public/kokteli/long.png',
        price: 38,
        class: 'cocktail',
        animationClass1: 'animation-div1',
        animationClass2: 'animation-div2',
        animationImage1: '/public/drink/longisland1.png',
        animationImage2: '/public/drink/longisland2.png',
      },
      {
        name: 'Sex on the Beach',
        image: './public/kokteli/sex.png',
        price: 36,
        class: 'cocktail',
        animationClass1: 'animation-div1',
        animationClass2: 'animation-div2',
        animationImage1: '/public/drink/sexonthebeach1.png',
        animationImage2: '/public/drink/sexonthebeach2.png',
      },
      {
        name: 'Old Fashioned',
        image: './public/kokteli/old.png',
        price: 35,
        class: 'cocktail',
        animationClass1: 'animation-div1',
        animationClass2: 'animation-div2',
        animationImage1: '/public/drink/oldfashioned1.png',
        animationImage2: '/public/drink/oldfashioned2.png',
      },
    ],
  },

  // {
  //   name: 'Smoothie i zdravi doručak',
  //   drinks: [
  //     {
  //       name: 'Smoothie od jagode',
  //       image: './public/drink/strawberry-smoothie.png',
  //       price: 18,
  //       class: 'smoothie',
  //       animationClass1: 'animation-div1',
  //       animationClass2: 'animation-div2',
  //       animationImage1: '/public/drink/smoothie1.png',
  //       animationImage2: '/public/drink/smoothie2.png',
  //     },
  //     {
  //       name: 'Zdravi doručak',
  //       image: './public/drink/healthy-breakfast.png',
  //       price: 25,
  //       class: 'breakfast',
  //       animationClass1: 'animation-div1',
  //       animationClass2: 'animation-div2',
  //       animationImage1: '/public/drink/breakfast1.png',
  //       animationImage2: '/public/drink/breakfast2.png',
  //     },
  //     // Dodajte ostale smoothie i zdravi doručak ovde...
  //   ],
  // },
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
  content: url('./public/drink/kava1.png');
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
