<template>
  <div class="sizes">
    <p class="title">Wymiary:</p>

    <p class="paragraph">
      Wysokosc:
      {{ this.package.height.value + " " + this.package.height.unit }}
    </p>
    <p>
      Szerokosc:
      {{ this.package.width.value + " " + this.package.width.unit }}
    </p>
    <p>
      Glebokosc:
      {{ this.package.depth.value + " " + this.package.depth.unit }}
    </p>
    <p>Waga:{{ this.package.weight.value + " " + this.package.weight.unit }}</p>
  </div>
</template>

<script>
export default {
  name: "Product-dimensions",
  data() {
    return {
      package: {
        height: {
          value: 110,
          unit: "mm",
        },
        width: {
          value: 380,
          unit: "mm",
        },
        depth: {
          value: 740,
          unit: "mm",
        },
        weight: {
          value: 5790,
          unit: "g",
        },
      },
    };
  },
};
</script>

<style scoped>
.sizes {
  /* border: #533ec9 1px solid; */
  /* border-radius: 12px; */
  margin-bottom: 15px;
  padding: 10px;
  text-align: center;
}
.paragraph {
  margin-top: 5px;
}

.title {
  /* padding: 10px; */
  display: flex;
  justify-content: center;
}
</style>
