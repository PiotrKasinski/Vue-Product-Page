<template>
  <div class="description">
    <p class="title">Opis produktu:</p>
    <p class="long-description">{{ description }}</p>
  </div>
</template>

<script>
export default {
  name: "Product-description",
  data() {
    return {
      description:
        "Wygodna deszczownica pozwala na swobodne ruchy pod prysznicem, gdyż nie musisz trzymać w ręku słuchawki. Tradycyjne kształty i nowoczesne wykończenie sprawiają, że ładnie prezentuje się w łazienkach industrialnych, skandynawskich, ale także w bardziej tradycyjnych wnętrzach. Trwała i wytrzymała powłoka jest odporna na odpryski i szok termiczny. Deszczownicę łatwo także utrzymać w nieskazitelnej czystości za sprawą systemu Anti-Calc. Osad kamienny z wody wykruszysz z silikonowych dysz jednym ruchem dłoni. W komplecie znajduje się także bateria prysznicowa. Za każdym razem możesz wybrać źródło wypływu wody i dobrać je do aktualnych potrzeb. Bateria jest elegancko wykończona i spójna z pozostałą częścią kolekcji oraz samą deszczownicą.",
    };
  },
};
</script>

<style scoped>
.description {
  /* border: #533ec9 1px solid; */
  /* border-radius: 12px; */
  margin-bottom: 15px;
  padding: 10px;
  text-align: justify;
}

.long-description {
  margin-top: 5px;
}
.title {
  padding: 10px;
  display: flex;
  justify-content: center;
}
</style>
