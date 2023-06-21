<!-- <template>
  <div>
    <div id="description" class="mt-4 col col-12">
      <div class="product-tabs">
        <div
          v-for="(tab, index) in tabs"
          :key="index"
          :class="['product-tab', { active: activeTab === index }]"
          @click="changeTab(index)"
        >
          {{ tab.name }}
        </div>
      </div>
    </div>

    <div id="product-content" class="mt-4">
      <div
        v-for="(tab, index) in tabs"
        :key="index"
        :id="tab.id"
        class="product-section"
        :class="{ active: activeTab === index }"
      ></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProductNavigation",
  props: {
    designersId: {
      type: String,
      default: "designers",
    },
    specificationId: {
      type: String,
      default: "properties",
    },
    downloadsId: {
      type: String,
      default: "files",
    },
  },
  data() {
    return {
      activeTab: 0, 
      tabs: [
        { name: "Opis produktu", id: "description" },
        { name: "Projektanci", id: this.designersId, hiddenSmAndDown: true },
        {
          name: "Specyfikacja produktu",
          id: this.specificationId,
          hiddenSmAndDown: true,
        },
        {
          name: "Pliki do pobrania",
          id: this.downloadsId,
          hiddenSmAndDown: true,
        },
        { name: "Polecane produkty", id: "recommended", hiddenSmAndDown: true },
      ],
    };
  },
  methods: {
    changeTab(index) {
      this.activeTab = index;
      this.scrollToSection(index);
    },
    scrollToSection(index) {
      const sectionId = this.tabs[index].id;
      const sectionElement = document.getElementById(sectionId);

      if (sectionId === this.designersId) {
        const designersComponent =
          document.getElementsByClassName("designer")[0];

        if (designersComponent) {
          designersComponent.scrollIntoView({ behavior: "smooth" });
        }
      } else if (sectionElement) {
        sectionElement.scrollIntoView({ behavior: "smooth" });
      }
    },
  },
};
</script>

<style scoped>
.product-tabs {
  display: flex;
}

.product-tab {
  cursor: pointer;
  padding: 10px;
  margin-right: 10px;
  background-color: #ccc;
}

.product-tab.active {
  background-color: #f54d4d;
  color: white;
}

.product-section {
  display: none;
}

.product-section.active {
  display: block;
}
</style> -->

<template>
  <div>
    <div id="description" class="mt-4 col col-12">
      <div class="product-tabs">
        <div
          v-for="(tab, index) in tabs"
          :key="index"
          :class="['product-tab', { active: activeTab === index }]"
          @click="changeTab(index)"
        >
          {{ tab.name }}
        </div>
      </div>
    </div>

    <div id="product-content" class="mt-4">
      <div
        v-for="(tab, index) in tabs"
        :key="index"
        :id="tab.id"
        class="product-section"
        :class="{ active: activeTab === index }"
      ></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProductNavigation",
  props: {
    designersId: {
      type: String,
      default: "designers",
    },
    specificationId: {
      type: String,
      default: "properties",
    },
    downloadsId: {
      type: String,
      default: "files",
    },
  },
  data() {
    return {
      activeTab: 0, // domyślnie aktywny pierwszy element
      tabs: [
        { name: "Opis produktu", id: "description" },
        { name: "Projektanci", id: this.designersId, hiddenSmAndDown: true },
        {
          name: "Specyfikacja produktu",
          id: this.specificationId,
          hiddenSmAndDown: true,
        },
        {
          name: "Pliki do pobrania",
          id: this.downloadsId,
          hiddenSmAndDown: true,
        },
      ],
    };
  },
  methods: {
    changeTab(index) {
      this.activeTab = index;
      this.scrollToSection(index);
    },
    scrollToSection(index) {
      const sectionId = this.tabs[index].id;
      const sectionElement = document.getElementById(sectionId);

      if (sectionId === this.designersId) {
        const designersComponent =
          document.getElementsByClassName("designer")[0];

        if (designersComponent) {
          designersComponent.scrollIntoView({ behavior: "smooth" });
        }
      } else if (sectionId === this.downloadsId) {
        const downloadsComponent = document.getElementsByClassName("files")[0];

        if (downloadsComponent) {
          downloadsComponent.scrollIntoView({ behavior: "smooth" });
        }
      } else if (sectionElement) {
        sectionElement.scrollIntoView({ behavior: "smooth" });
      }
    },
  },
};
</script>

<style scoped>
.product-tabs {
  display: flex;
  justify-content: center;
}

.product-tab {
  cursor: pointer;
  padding: 10px;
  margin-right: 10px;
  background-color: white;
}

.product-tab.active {
  background-color: #ccc;
  color: white;
}

.product-section {
  display: none;
}

.product-section.active {
  display: block;
}
</style>
