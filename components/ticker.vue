<script setup>
import { ref, onMounted } from "vue"
const infos = ref([
  "Au revoir Axel, tu vas nous manquer bb!",
  "Curiosité: le mot 'sabotage' vient de l'expression 'saboter un sabot' qui signifie 'mettre un sabot dans une machine pour la bloquer'.",
  "Le saviez-vous ? Les éléphants sont les seuls animaux qui ne peuvent pas sauter.",
  "Actualité: le gouvernement français a annoncé un plan de relance de 10 euros pour l'économie.",
  "Une étude scientifique a prouvé que les chevaux sont des connards."
])
</script>

<template>
  <div class="ticker-wrap">
    <div class="ticker">
      <p v-for="info in infos" class="ticker__item mr-[300px]"> {{ info }} </p>
    </div>
  </div>
</template>

<style lang="scss">
  * { box-sizing: border-box; }
  $duration: 30s;

  @-webkit-keyframes ticker {
    0% {
      -webkit-transform: translate3d(0, 0, 0);
      transform: translate3d(0, 0, 0);
      visibility: visible;
    }

    100% {
      -webkit-transform: translate3d(-100%, 0, 0);
      transform: translate3d(-100%, 0, 0);
    }
  }

  @keyframes ticker {
    0% {
      -webkit-transform: translate3d(0, 0, 0);
      transform: translate3d(0, 0, 0);
      visibility: visible;
    }

    100% {
      -webkit-transform: translate3d(-100%, 0, 0);
      transform: translate3d(-100%, 0, 0);
    }
  }

  .ticker-wrap {
    position: fixed;
    bottom: 0;
    width: 100%;
    overflow: hidden;
    height: 4rem;
    background-color: rgba(#000000, 0.9); 
    padding-left: 100%;
    box-sizing: content-box;

    .ticker {

      display: inline-block;
      height: 4rem;
      line-height: 4rem;  
      white-space: nowrap;
      padding-right: 100%;
      box-sizing: content-box;

      -webkit-animation-iteration-count: infinite; 
              animation-iteration-count: infinite;
      -webkit-animation-timing-function: linear;
              animation-timing-function: linear;
    -webkit-animation-name: ticker;
            animation-name: ticker;
      -webkit-animation-duration: $duration;
              animation-duration: $duration;

      &__item {

        display: inline-block;

        padding: 0 2rem;
        font-size: 2rem;
        color: white;   

      }

    }

  }


</style>