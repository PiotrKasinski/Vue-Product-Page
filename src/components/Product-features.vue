<template>
  <div class="features">
    <!-- <div v-for="feature in features" :key="feature.name">
      <div class="feature-content"> -->
    <div
      v-for="(feature, index) in features"
      :key="feature.name"
      class="feature-item"
    >
      <!-- <div :class="['feature-content', index % 2 === 1 ? 'reverse' : '']"> -->
      <div
        :class="[
          'feature-content',
          index % 2 === 1 ? 'reverse' : '',
          isSmallScreen ? 'hide-details' : '',
        ]"
      >
        <img class="feature-image" :src="feature.image" alt="" />
        <div class="title-details">
          <h2 class="feature-title">{{ feature.name }}</h2>
          <p class="feature-details">{{ feature.description }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Product-features",
  data() {
    return {
      features: [
        // {
        //   name: "Drążek wykonany ze stali",
        //   description: "",
        //   image: "",
        // },
        // {
        //   name: "Tylko najlepsze materiały, których jakość potwierdzamy badaniami w laboratorium",
        //   description: "",
        //   image: "",
        // },
        {
          name: "3-funkcyjna słuchawka",
          description:
            "W zależności od życzenia możesz wybrać jeden z trzech rodzajów strumienia: deszczowy, mieszany i hydromasaż, które zmienia się dyskretnym, a zarazem ergonomicznym przełącznikiem. Codzienne korzystanie z wody stanie się szczególnym rytuałem.",
          image:
            "https://media.deante.pl/decor/_MARKETING/WYROZNIKI/AGAWA/3-funkcyjna-sluchawka.jpg",
        },
        {
          name: "Asymetryczny, regulowany drążek",
          description:
            "Asymetryczne ustawienie drążka względem baterii, nadaje deszczowni szczególnego charakteru. Regulowany drążek pozwala na precyzyjne ustawienie wysokości deszczowni do potrzeb użytkownika. Te ciekawe rozwiązania wprowadzają nowy wymiar komfortu do strefy prysznica.",
          image:
            "https://media.deante.pl/decor/_MARKETING/WYROZNIKI/AGAWA/asymetryczny-regulowany-drazek.jpg",
        },
        {
          name: "Unikatowy design",
          description:
            "Linia Agawa projektu Marii Warenik to połączenie estetyki z funkcjonalnością i ergonomią. Elegancka, minimalistyczna, a zarazem solidna i długowieczna w użytkowaniu. Precyzyjnie uformowane powierzchnie i krawędzie są przyjemne dla zmysłu dotyku. Armatura pozbawiona zakamarków jest łatwa do utrzymania w czystości. Ponadczasowe chromowane wykończenie linii Agawa czyni z niej rozwiązanie idealne do każdej łazienki. ",
          image:
            "https://media.deante.pl/decor/_MARKETING/WYROZNIKI/AGAWA/agawa-design.jpg",
        },
        {
          name: "Duża słuchawka prysznicowa",
          description:
            "Dużą, wygodną słuchawkę prysznicową można z powodzeniem używać zamiennie z deszczownią. Jej przewagą jest możliwość kierowania strumieniem wody na dowolnej wysokości. Tym sposobem zarówno dziecko, jak i osoba dorosła, wykąpią się z łatwością. Możesz bez problemu wziąć prysznic, nawet jeśli nie chcesz zamoczyć włosów. ",
          image:
            "https://media.deante.pl/decor/_MARKETING/WYROZNIKI/AGAWA/duza-sluchawka.jpg",
        },
        {
          name: "Słuchawka z funkcją Anti-calc",
          description:
            "Silikonowe wypustki przeciwdziałają osadzaniu się kamienia i tym samym przedłużają trwałość i niezawodność działania słuchawki natryskowej. Wystarczy przetrzeć je palcem, a osady z kamienia znikają w mgnieniu oka. ",
          image:
            "https://media.deante.pl/decor/_MARKETING/WYROZNIKI/AGAWA/funkcja-anti-calc-przeciwdziala-osadzaniu-sie-kamienia.jpg",
        },
        {
          name: "Regulowany kąt nachylenia słuchawki",
          description:
            "Deszczownia posiada ruchomy uchwyt na słuchawkę, dzięki temu możemy regulować kąt nachylenia główki prysznicowej. ",
          image:
            "https://media.deante.pl/decor/_MARKETING/WYROZNIKI/AGAWA/regulowany-kat-nachylenia-sluchawki.jpg",
        },
        {
          name: "Rotacyjny, mechaniczny przełącznik funkcji",
          description:
            "Dyskretny, a jednocześnie bardzo ergonomiczny przełącznik funkcji, który umożliwia zmianę wypływu strumienia wody nawet przy niskim ciśnieniu.",
          image:
            "https://media.deante.pl/decor/_MARKETING/WYROZNIKI/AGAWA/rotacyjny-mechaniczny-przelacznik-funkcji.jpg",
        },
        {
          name: "Stalowa głowica natryskowa",
          description:
            "Ultra cienka głowica ma aż 30 cm, co stanowi gwarancję przyjemnej, relaksującej kąpieli pod prysznicem. Ponadto głowica wyposażona jest w system Anti-calc i posiada w zestawie wymienne „gumki”.",
          image:
            "https://media.deante.pl/decor/_MARKETING/WYROZNIKI/AGAWA/stalowa-glowica-natryskowa.jpg",
        },
        {
          name: "W ofercie dedykowany środek bezpieczny dla czyszczonych powierzchni",
          description:
            "Użycie dedykowanych środków powoduje, że powierzchnie nie niszczą się i długo pozostają gładkie, ułatwiając codzienne sprzątanie. Specjalnie dobrany skład usuwa najczęściej spotykane zabrudzenia niezwykle skutecznie. Z drugiej strony preparaty są łagodne dla danego typu nawierzchni (metal, granit, ceramika i inne), nie wchodząc z nimi w reakcje chemiczne. Preparaty są biodegradowalne i tym samym bezpieczne dla środowiska. Ze środkami do czyszczenia Deante utrzymanie nienagannego porządku będzie niezwykle proste!",
          image:
            "https://media.deante.pl/decor/_MARKETING/WYROZNIKI/CHEMIA/srodek-chemiczny-bezpieczny-dla-czyszczonych-powierzchni.jpg",
        },
        {
          name: "Regulowana wysokość deszczownicy",
          description:
            "Deszczownia posiada regulowaną wysokość głowicy górnej, która umożliwia dopasowanie jej do wzrostu użytkownika. Ten zakres umożliwia optymalne ustawienie wysokości deszczownicy dla wszystkich domowników. ",
          image:
            "https://media.deante.pl/decor/_MARKETING/WYROZNIKI/NATRYSKI/regulowana-wysokosc-deszczownicy.jpg",
        },
        // {
        //   name: "Dostępne dedykowane preparaty, ułatwiające pielęgnację produktów",
        //   description: "",
        //   image: "",
        // },
        // {
        //   name: "Korpus baterii wykonany z najwyższej jakości mosiądzu",
        //   description: "",
        //   image: "",
        // },
      ],
      isSmallScreen: false,
    };
  },
  mounted() {
    this.checkScreenSize();

    window.addEventListener("resize", this.checkScreenSize);
  },
  beforeUnmount() {
    window.removeEventListener("resize", this.checkScreenSize);
  },
  methods: {
    checkScreenSize() {
      this.isSmallScreen = window.innerWidth <= 600;
    },
  },
};
</script>

<style scoped>
.features {
  /* border: #f54d4d 1px solid; */
  border-radius: 12px;
  padding: 10px;
  margin-bottom: 15px;
  display: flex;
  flex-direction: column;
}
.features p {
  margin: 5px;
  /* border-bottom: 1px solid black; */
}

.feature-image {
  max-width: 200px;
  max-height: 200px;
  border-radius: 12px;
}
.feature-content {
  display: flex;
  flex-direction: row;
  align-items: center;
  margin-bottom: 15px;
}
.title-details {
  margin: 10px;
}
.feature-title {
  margin-bottom: 10px;
}

.reverse {
  flex-direction: row-reverse;
}
@media (max-width: 600px) {
  .hide-details .feature-details {
    display: none;
  }
}
</style>
