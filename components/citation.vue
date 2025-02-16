<script setup>
import { ref, computed, onMounted } from "vue"

const quotes = ref([
    {
        date: "25/10/2023",
        user: "gaetan",
        string: "J'ai une couille."
    },
    {
        date: "06/10/2023",
        user: "elie",
        string: "Château-Rouge c'est le Lidl des léchouilles."
    },
    {
        date: "06/10/2023",
        user: "julie",
        string: "Une léchouille pour 3000 balles ?"
    },
    {
        date: "27/10/2023",
        user: "juliana",
        string: "Tu veux que je vienne m'astiquer un peu à côté de toi ?"
    },
    {
        date: "23/10/2023",
        user: "laurentina",
        string: "Hmmm... J'en ai plein la bouche."
    },
    {
        date: "12/09/2023",
        user: "laurentina",
        string: "Vincent a un caractère de meuf menstruée tout le temps."
    },
    {
        date: "01/09/2023",
        user: "adrien",
        string: "Mathilde, sa spécialité, c'est par derrière."
    },
    {
        date: "20/10/2023",
        user: "jesse",
        string: "T'as envie de lui casser le coquillage !"
    },
    {
        date: "08/09/2023",
        user: "axel",
        string: "Tu veux bien laisser mes testicules tranquilles ?"
    },
    {
        date: "29/09/2023",
        user: "nicolas",
        string: "Pourquoi on se touche pas ici ?"
    },
    {
        date: "09/10/2023",
        user: "adrien",
        string: "Tu te rappel de la forme de ton caca il y'a 4 mois ?"
    },
    {
        date: "22/09/2023",
        user: "flora",
        string: "J'ai plus de thunes... j'ai tout bu."
    },
    {
        date: "",
        user: "nicolas",
        string: "Moi, je ne bois plus de bière à la maison, que au bureau."
    },
    {
        date: "",
        user: "benjamin",
        string: "Le nombre de fois où je me suis sorti d'une merde en allant chier..."
    },
    {
        date: "20/09/2023",
        user: "jesse",
        string: "Quel bâtard de fils de pute !"
    },
    {
        date: "24/10/2023",
        user: "adrien",
        string: "T'es tout serré de partout, du coup ca manque d'air."
    },
    {
        date: "",
        user: "adrien",
        string: "- Lazar, combien tu prends pour t'en débarasser ?\n- 30 minutes."
    },
    {
        date: "24/08/2023",
        user: "clemence",
        string: "Ça te perturberait pas, si tu lattes un mec dans les couilles et il jouit ?"
    },
    {
        date: "15/10/2023",
        user: "axel",
        string: "Ça peut rentrer à 4."
    },
    {
        date: "29/08/2023",
        user: "julie",
        string: "En 30 minutes, j'te démonte"
    },
    {
        date: "03/10/2023",
        user: "laurentina",
        string: "Je crache pas, je projette"
    },
    {
        date: "20/10/2023",
        user: "jesse",
        string: "J’aime quand tu parles sale"
    },
    {
        date: "20/10/2023",
        user: "nicolas",
        string: "Si tu te lèves trop vite, j’aurais mal aux couilles"
    },
    {
        date: "29/09/2023",
        user: "laurentina",
        string: "Je reconnais l’odeur de ton truc"
    },
    {
        date: "20/10/2023",
        user: "laurentina",
        string: "J’vais l’introduire comme il faut"
    },
    {
        date: "07/09/2023",
        user: "nicolas",
        string: "Me fais pas rire, je vais péter !"
    },
    {
        date: "07/09/2023",
        user: "nicolas",
        string: "Vous avez jamais un gros tas de caca en plein de morceaux et ça fait un cerveau ?"
    },
    {
        date: "14/09/2023",
        user: "elie",
        string: "Ça va... C’est que de l’API"
    },
    {
        date: "",
        user: "adrien",
        string: "Est-ce que ça solutionnerait pas le problème si on s’en bât les couilles ?"
    },
    {
        date: "01/09/2023",
        user: "axel",
        string: "Je vous contrôle tous avec ma micro bite... d’accord"
    },
    {
        date: "04/10/2023",
        user: "adrien",
        string: "Vincent, j’ai besoin de ton doigt !"
    },
    {
	date: "25/07/2023",
	user: "nicolas",
	string: "Hello il y a un orage à tournan ma soeur a taxer mon parapluie hier je reste en TT"
    },
    {
	date: "31/08/2023",
	user: "jane",
	string: "Ça y est, tu t’es retiré là ?"
    },
    {
	date: "24/10/2023",
	user: "gaetan",
	string: "Elle donne quoi la grosse paire de Lazar ?"
    },
    {
	date: "25/10/2023",
	user: "juliana",
	string: "Hier, j’ai croisé Adrien dans la rue, il étais déjà tout dur"
    },
    {
	date: "31/08/2023",
	user: "jane",
	string: "Avant on vérifie combien vous êtes là-dedans..."
    },
    {
	date: "Tous les jours",
	user: "adrien",
	string: "MARGES !"
    },
    {
	date: "28/08/2023",
	user: "nicolas",
	string: "Adrien, t’as acheté un four et on peut même pas faire des merguez dedans !"
    },
    {
	date: "20/10/2023",
	user: "laurentina",
	string: "Moi je mouille avant et après"
    },
    {
	date: "19/10/2023",
	user: "adrien",
	string: "Nan... ça pue quand tu écartes..."
    },
    {
	date: "09/10/2023",
	user: "elie",
	string: "Je m’astique fort, j’adore ça !"
    },
    {
	date: "30/09/2023",
	user: "jesse",
	string: "Dieu, c’est ma pute"
    },
    {
	date: "",
	user: "nicolas",
	string: "la deusieme page d’uitlisateur ne s’affiche pas on peux voir quil y a d’autre utilise qui si on augmente la vision de 25 à 50"
    },
    {
	date: "04/09/2023",
	user: "ben",
	string: "Je sais pas comment te déboucher"
    },
    {
	date: "27/10/2023",
	user: "adrien",
	string: "J’ai de la merde dans mes tiroirs"
    },
    {
	date: "27/10/2023",
	user: "clemence",
	string: "C’est gênant... Il me regarde dans les yeux en bougeant sa couille"
    },
    {
	date: "13/10/2023",
	user: "vincent",
	string: "Putain mais comment ils ont branlé leurs rapports ?!"
    },
    {
	date: "25/10/2023",
	user: "nicolas",
	string: "Dans ton trou tu mets la bouteille..."
    },
    {
	date: "16/10/2023",
	user: "axel",
	string: "Nico, je vais t’arracher les couilles et te les enfoncer dans la gorge "
    },
    {
	date: "26/09/2023",
	user: "thomas",
	string: "un seul t à bouton ;-)"
    },
    {
	date: "30/10/2023",
	user: "gaetan",
	string: "Tu l’as dans le hook"
    },
    {
	date: "30/10/2023",
	user: "clemence",
	string: "Bah y’a différents formats, faut juste réussir à les faire rentrer"
    },
    {
	date: "31/10/2023",
	user: "flora",
	string: "Ils vont bien glisser dans ta gorge ce soir."
    },
])

const currentIndex = ref(0)
const currentQuote = ref(quotes.value[currentIndex.value])
const isAnimatingOut = ref(false)

// const animationKey = ref(0)

const changeQuote = () => {
  isAnimatingOut.value = true

  setTimeout(() => {
    currentIndex.value = (currentIndex.value + 1) % quotes.value.length
    currentQuote.value = quotes.value[currentIndex.value]

    isAnimatingOut.value = false

  }, 400)
}

onMounted(() => {
  setInterval(changeQuote, 30000)
})
</script>

<template>
  <div>
    <div 
      class="citation" 
      :class="{ 'fade-in': !isAnimatingOut }"
    >
      <Icon name="ph:quotes-fill" id="quote-open" />
      <div class="content">
        <p>{{ currentQuote.string }}</p>
        <p class="text-end">— {{ currentQuote.user }}</p>
        <p class="text-xl text-end"> {{ currentQuote.date }}</p>
      </div>
      <Icon name="ph:quotes-fill" id="quote-close" />
    </div>
  </div>
</template>

<style lang="scss">
.citation {
  position: absolute;
  top: 50%;
  left: 50%;
  width: fit-content;
  transform: translate(-50%, -50%);

  .content {
    font-size: 3.5rem;
    color: black;
    text-align: center;
    background-color: rgba(#e8e8efb3, 0.9);
    padding: 2rem;
    // animation: expand 390ms ease-out forwards;
  }

  #quote-open, #quote-close {
    font-size: 10rem;
    position: absolute;
    z-index: 2;
  }

  #quote-open {
    left: -95px;
    top: -95px;
    transform: rotate(180deg);
    // animation: moveQuoteOpen 390ms ease-out forwards;
  }

  #quote-close {
    right: -95px;
    bottom: -95px;
    // animation: moveQuoteClose 390ms ease-out forwards;
  }
}

// Animation d'apparition
@keyframes expand {
  0% {
    transform: scale(0.1);
    opacity: 0;
  }
  20% {
    opacity: 0;
  }
  100% {
    transform: scale(1);
    opacity: 1;
  }
}

// Animation des icônes
@keyframes moveQuoteOpen {
  0% {
    left: 50%;
    top: 49%;
    transform: translate(-50%, -50%) rotate(180deg);
  }
  100% {
    left: -95px;
    top: -95px;
    transform: rotate(180deg);
  }
}

@keyframes moveQuoteClose {
  0% {
    right: 50%;
    bottom: 49%;
    transform: translate(50%, 50%);
  }
  100% {
    right: -95px;
    bottom: -95px;
  }
}

// Animation d'apparition
.fade-in {
  .content {
    animation: expand 390ms ease-out forwards;
  }

  #quote-open {
    animation: moveQuoteOpen 390ms ease-out forwards;
  }

  #quote-close {
    animation: moveQuoteClose 390ms ease-out forwards;
  }
}
</style>
