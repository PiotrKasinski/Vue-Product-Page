<template>
  <div class="files">
    <p class="title">Pliki do pobrania:</p>
    <div class="inProperties" v-for="file in files" :key="file.name">
      <p>{{ file.type }}</p>
      <a v-bind:href="file.src" download target="_blank">Pobierz</a>
    </div>
  </div>
</template>

<script>
export default {
  name: "Download-files",
  data() {
    return {
      files: [
        {
          src: "https://pc21.deante.pl/NATRYSKI/_DESZCZOWNIE/AGAWA_01QG/NAC_01QG.pdf",
          type: "technicalDrawing",
        },
        {
          src: "https://pc21.deante.pl/_INSTRUKCJE/czyszczenie_dysz_cleaning_nozzles_manual.pdf",
          type: "instruction",
        },
        {
          src: "https://pc21.deante.pl/_INSTRUKCJE/konserwacja_natryski_conservation_showers_manual.pdf",
          type: "instruction",
        },
        {
          src: "https://pc21.deante.pl/_INSTRUKCJE/piel%C4%99gnacja_powierzchni_armatura_natryski_surface_care_for_fittings_manual.pdf",
          type: "instruction",
        },
        {
          src: "https://pc21.deante.pl/_INSTRUKCJE/NAC_01QG_manual.pdf",
          type: "instruction",
        },
        {
          src: "https://pc21.deante.pl/NATRYSKI/_DESZCZOWNIE/AGAWA_01QG/NAC_01QG.dxf",
          type: "model3d",
        },
        {
          src: "https://pc21.deante.pl/NATRYSKI/_DESZCZOWNIE/AGAWA_01QG/NAC_01QG.obj",
          type: "model3d",
        },
        {
          src: "https://pc21.deante.pl/NATRYSKI/_DESZCZOWNIE/AGAWA_01QG/NAC_01QG.dae",
          type: "model3d",
        },
        {
          src: "https://pc21.deante.pl/NATRYSKI/_DESZCZOWNIE/AGAWA_01QG/NAC_01QG.skp",
          type: "model3d",
        },
        {
          src: "https://pc21.deante.pl/_GWARANCJE/Deante_Gwarancje_Warranty-od-18_05_2021-_19287.pdf",
          type: "warrantyCard",
        },
        {
          src: "https://pc21.deante.pl/_ATESTY/Atest-PZH-Natryski.pdf",
          type: "hygienicCertificate",
        },
        {
          src: "https://pc21.deante.pl/_DEKLARACJE/Natryski/DWU%20deszczownie%20mieszaczowe.pdf",
          type: "declaration",
        },
      ],
    };
  },
};
</script>

<style scoped>
.inProperties {
  display: flex;
  justify-content: space-between;
  border-bottom: 1px solid #b7b7b7;
  vertical-align: baseline;
}

.files {
  /* border: #cd89d4 1px solid; */
  /* border-radius: 12px; */
  padding: 10px;
  margin-bottom: 15px;
}

.files a {
  border: black 1px solid;
  border-radius: 12px;
  padding: 5px;
  margin: 2px;
  text-decoration: none;
  color: black;
  background-color: #f2f2f2;
}

.title {
  /* padding: 10px; */
  display: flex;
  justify-content: center;
}
</style>
