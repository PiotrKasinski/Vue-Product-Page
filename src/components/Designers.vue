<template>
  <div class="designer">
    <p v-if="isDesigned === true" class="title">Projektanci:</p>
    <div v-for="designer in designers" :key="designer.name">
      <h3>{{ designer.name }}</h3>
      <p>{{ designer.description }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Product-designers",
  data() {
    return {
      isDesigned: true,
      designers: [
        {
          name: "Maria Warenik",
          description:
            "Absolwentka kierunku Product Design na Akademii Sztuk Pięknych w Gdańsku. Specjalizuje się w formie, kształcie, proporcjach oraz przenikaniu płaszczyzn w przestrzeni. Zdaniem projektantki przedmioty powinny być estetyczne, dawać zadowolenie i cieszyć swoim widokiem, najważniejsze są jednak wygoda i intuicyjna obsługa.",
        },
      ],
    };
  },
};
</script>

<style>
.designer {
  /* border: #ae1a61 1px solid; */
  /* border-radius: 12px; */
  margin-bottom: 15px;
  padding: 10px;
  text-align: justify;
}

.designer h3 {
  text-align: center;
}

.title {
  padding: 10px;
  display: flex;
  justify-content: center;
}
</style>
