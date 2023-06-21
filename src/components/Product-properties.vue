<template>
  <div class="properties">
    <div v-for="group in groupedProperties" :key="group.scope">
      <p class="custom-bg-color">{{ group.scope }}</p>
      <div
        class="inProperties"
        v-for="property in group.properties"
        :key="property.name"
      >
        <!-- <p v-for="property in group.properties" :key="property.name">
          {{ property.name + ": " + property.value }}
        </p> -->
        <p>{{ property.name + ": " }}</p>
        <p>{{ property.value }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Product-Properties",
  data() {
    return {
      properties: [
        {
          name: "Wykończenie",
          value: "chrom",
          scope: "DESZCZOWNICA",
        },
        {
          name: "Bateria",
          value: "Tak",
          scope: "DESZCZOWNICA",
        },
        {
          name: "Klasa przepływu [l/min]",
          value: "Z - 7.2-11.9 l/min",
          scope: "DESZCZOWNICA",
        },
        {
          name: "Regulowana wysokość górnej deszczowni",
          value: "Tak",
          scope: "DESZCZOWNICA",
        },
        {
          name: "Regulacja wysokości drążka od [mm]",
          value: 860,
          scope: "DESZCZOWNICA",
        },
        {
          name: "Regulacja wysokości drążka do [mm]",
          value: 1190,
          scope: "DESZCZOWNICA",
        },
        {
          name: "Materiał",
          value: "stal 304",
          scope: "DRĄŻEK",
        },
        {
          name: "Dodatkowe cechy",
          value: "regulowany kąt ustawienia słuchawki natryskowej",
          scope: "DRĄŻEK",
        },
        {
          name: "Kształt",
          value: "okrągły",
          scope: "GŁOWICA NATRYSKOWA",
        },
        {
          name: "Materiał",
          value: "stal 304, mosiądz",
          scope: "GŁOWICA NATRYSKOWA",
        },
        {
          name: "Grubość [mm]",
          value: 55,
          scope: "GŁOWICA NATRYSKOWA",
        },
        {
          name: "Średnica [mm]",
          value: 300,
          scope: "GŁOWICA NATRYSKOWA",
        },
        {
          name: "Anti-calc",
          value: "Tak",
          scope: "GŁOWICA NATRYSKOWA",
        },
        {
          name: "Ilość funkcji",
          value: "1",
          scope: "GŁOWICA NATRYSKOWA",
        },
        {
          name: "Rodzaje strumienia",
          value: "deszczowy",
          scope: "GŁOWICA NATRYSKOWA",
        },
        {
          name: "Szybki czas reakcji na włączenie i wyłączenie wody",
          value: "Tak",
          scope: "GŁOWICA NATRYSKOWA",
        },
        {
          name: "Ilość funkcji",
          value: "3",
          scope: "SŁUCHAWKI",
        },
        {
          name: "Anti-calc",
          value: "Tak",
          scope: "SŁUCHAWKI",
        },
        {
          name: "Rodzaje strumienia",
          value: "deszczowy, mieszany, hydromasaż",
          scope: "SŁUCHAWKI",
        },
        {
          name: "Długość [mm]",
          value: "1500",
          scope: "WĘŻE",
        },
        {
          name: "Materiał oplotu",
          value: "PVC",
          scope: "WĘŻE",
        },
        {
          name: "Anti-twist",
          value: "1",
          scope: "WĘŻE",
        },
        {
          name: "Typ przełącznika",
          value: "mechaniczny ceramiczny",
          scope: "PRZEŁĄCZNIK FUNKCJI",
        },
        {
          name: "Rodzaj baterii",
          value: "mieszaczowa, jednouchwytowa",
          scope: "BATERIA",
        },
        {
          name: "Gwarancja",
          value: "5 Lat",
        },
      ],
    };
  },
  computed: {
    groupedProperties() {
      const grouped = {};
      for (const property of this.properties) {
        if (!grouped[property.scope]) {
          grouped[property.scope] = {
            scope: property.scope,
            properties: [],
          };
        }
        grouped[property.scope].properties.push(property);
      }
      return Object.values(grouped);
    },
  },
};
</script>

<style scoped>
.properties {
  /* border: #291aae 1px solid; */
  /* border-radius: 12px; */
  margin-bottom: 15px;
  padding: 10px;
}

.inProperties {
  display: flex;
  justify-content: space-between;
  border-bottom: 1px solid #b7b7b7;
}
</style>
