<template>
  <div class="tabs">
    <div class="tabLinks">
      <span
        class="tab"
        v-for="(tab, index) in tabs"
        :key="index"
        @click="selectedTabs = tab"
        :class="{ activeTab: selectedTabs === tab }"
        >{{ tab }}</span
      >
    </div>
    <div class="tabContent">
      <div class="reviews" v-show="selectedTabs === 'Reviews'">
        <h2>Reviews</h2>
        <p v-if="!reviews.length">There are no reviews yet.</p>
        <ul>
          <li v-for="(review, index) in reviews" :key="index">
            <p>{{ review.review }}</p>
            <span
              >{{ review.name }}, <strong>Rating: </strong
              >{{ review.rating }}</span
            >
          </li>
        </ul>
      </div>
      <product-review @review-submited="addReview" />
    </div>
  </div>
</template>

<script>
import ProductReview from "./Product-review.vue";
export default {
  name: "Product-tabs",
  components: { ProductReview },
  props: {
    reviews: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {
      tabs: ["Reviews", "Make a review"],
      selectedTabs: "Reviews",
    };
  },
};
</script>
