<template>
  <div
    class="d-flex flex-column w-full pa-4 pa-md-12 fade-container"
    ref="fadeContainer"
    data-aos="fade-up"
    data-aos-duration="1000"
    data-aos-easing="ease-in-circ"
  >
    <article class="mb-7">
      <ProjectTemplate
        v-for="(project, index) in projects.projects"
        :key="index"
        :project-detail="project"
      />
    </article>
  </div>
</template>

<script setup>
import { ref } from "vue";
import ProjectTemplate from "./ProjectTemplate.vue";
import projects from "../data/projects.json";

const fadeContainer = ref();
</script>

<style scoped lang="scss">
:deep() {
  background-color: #d3d3d3 !important;
  .subtitle {
    font-size: 34px;
  }

  .paragraph p {
    line-height: 30px;
  }

  @media (min-width: 961px) {
    .subtitle {
      font-size: 48px;
    }

    .paragraph p {
      line-height: 34px;
      font-size: 20px;
    }
  }
}
</style>