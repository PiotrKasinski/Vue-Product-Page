<template>
  <div>
    <div class="container">
      <h1>{{ title }}</h1>
      <div style="display: flex">
        <p style="margin-right: 25px">Nr Kat: {{ id }}</p>
        <p>Marka: {{ brand }}</p>
      </div>
      <div class="galeryAndContent">
        <div class="product">
          <div class="image">
            <img v-bind:src="productImage" />
          </div>

          <div class="content" v-if="!isSmallScreen">
            <div class="variants">
              <span
                v-for="(variant, index) in variants"
                :key="variant.variantId"
                @click="updateImage(index)"
                @mouseover="updateImage(index)"
                class="colorBox"
              >
                <img v-bind:src="variant.variantImage"
              /></span>
            </div>

            <div class="stockInfo">
              <span class="green" v-if="inventory > 10">W magazynie</span>
              <span class="amber" v-else-if="inventory <= 10 && inventory > 0">
                Ostatnie sztuki
              </span>
              <span class="red" v-else>Out of stock</span>
            </div>
            <ul class="finishes">
              Wykonczenie:
              <li v-for="(finish, index) in finishes" :key="index">
                {{ finish }}
              </li>
            </ul>

            <div>
              <div v-for="category in categories" :key="category.id">
                <!-- <p v-if="category.main">{{ category.id }}</p> -->
                <p v-if="category.main">Kategoria: {{ category.name }}</p>
              </div>
            </div>
            <!-- <div class="shipping">Shipping: {{ shipping }}</div> -->
            <div class="pices" style="display: inline-flex">
              <h1>{{ price }}</h1>
              <h3>{{ priceNet }}</h3>
            </div>
            <div class="addCart">
              <button
                v-on:click="addToCart"
                :disabled="inventory <= 0"
                :class="{ disabledState: inventory <= 0 }"
              >
                Dodaj do koszyka
              </button>
            </div>
          </div>
        </div>
      </div>

      <SiteNav :tabs="tabs" />
      <Description />
      <Dimensions />
      <ProductFeatures />
      <SiteNav :tabs="tabs" />
      <Designers />
      <ProductProperties />
      <SiteNav :tabs="tabs" />
      <DownloadFiles />

      <product-tabs :reviews="reviews" />
    </div>
  </div>
</template>

<script>
import ProductTabs from "./Product-tabs.vue";
import Description from "./Description.vue";
import Dimensions from "./Dimensions.vue";
import Designers from "./Designers.vue";
import ProductProperties from "./Product-properties.vue";
import DownloadFiles from "./Download-files.vue";
import ProductFeatures from "./Product-features.vue";
import SiteNav from "./Site-nav.vue";
export default {
  components: {
    ProductTabs,
    Description,
    Dimensions,
    Designers,
    ProductProperties,
    DownloadFiles,
    ProductFeatures,
    SiteNav,
  },
  name: "Product-page",
  props: {
    member: {
      type: Boolean,
      required: true,
    },
  },
  data() {
    return {
      id: "NAC_01QG",
      brand: " Deante",
      product: " Deszczownica z baterią prysznicową",
      selectedVariant: 0,
      collection: "Agawa",
      finishes: [
        "Drążek wykonany ze stali",
        "Tylko najlepsze materiały, których jakość potwierdzamy badaniami w laboratorium",
        "3-funkcyjna słuchawka",
        "Asymetryczny, regulowany drążek",
        "Unikatowy design",
        "Duża słuchawka prysznicowa",
        "Słuchawka z funkcją Anti-calc",
        "Regulowany kąt nachylenia słuchawki",
        "Rotacyjny, mechaniczny przełącznik funkcji",
        "Stalowa głowica natryskowa",
        "W ofercie dedykowany środek bezpieczny dla czyszczonych powierzchni",
        "Regulowana wysokość deszczownicy",
      ],
      prices: {
        currency: "PLN",
        netPrice: 1056.1,
        grossPrice: 1299,
        vat: 23,
        hasPromotion: true,
        promotion: {
          netPrice: 974.8,
          grossPrice: 1199,
        },
      },
      categories: [
        {
          id: "ŁAZIENKA/PRYSZNIC/DESZCZOWNICE",
          main: true,
          name: "Łazienka/Prysznice/Deszczownice",
        },
        {
          id: "ŁAZIENKA",
          main: false,
          name: "Łazienka",
        },
        {
          id: "ŁAZIENKA/PRYSZNIC",
          main: false,
          name: "Łazienka/Prysznice",
        },
      ],

      variants: [
        {
          variantId: 1,
          variantImage:
            "https://media.deante.pl/decor/NATRYSKI/_DESZCZOWNIE/AGAWA_01QG/NAC_01QG.jpg",
          variantQty: 20,
        },
        {
          variantId: 2,
          variantImage:
            "https://media.deante.pl/decor/ARANZE/RGB_BQG_054L%2C-ADR_0411%2C-ADR_0121%2C-CQR_SU6S%2C-CKC_N90A%2C-NHC_031K%2C-KTA_032P%2C-NAC_01QG%2C-ADM_A54K%2C-KON_008S.jpg",
          variantQty: 20,
        },
        {
          variantId: 3,
          variantImage: "https://media.deante.pl/decor/ARANZE/RGB_NAC_01QG.jpg",
          variantQty: 20,
        },
      ],
      reviews: [],
      warranty: 5,
      isSmallScreen: false,
    };
  },

  created() {
    this.isSmallScreen = window.innerWidth <= 768;
  },

  mounted() {
    window.addEventListener("resize", this.checkScreenWidth);
  },

  destroyed() {
    window.removeEventListener("resize", this.checkScreenWidth);
  },

  methods: {
    addToCart() {
      this.$emit("addtocart", this.variants[this.selectedVariant].variantId);
    },
    updateImage(index) {
      this.selectedVariant = index;
    },
    addReview(productReview) {
      this.reviews.push(productReview);
    },
    checkScreenSize() {
      this.isSmallScreen = window.innerWidth <= 600;
    },
  },
  // computed properties
  computed: {
    title() {
      return this.product;
    },
    productImage() {
      return this.variants[this.selectedVariant].variantImage;
    },
    inventory() {
      return this.variants[this.selectedVariant].variantQty;
    },
    shipping() {
      if (this.member) {
        return "Free";
      }
      return "$" + 2.99;
    },
    price() {
      return this.prices.grossPrice + " " + this.prices.currency;
    },
  },
};
</script>
