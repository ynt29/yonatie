<template>
  <div class="mb-12 d-flex flex-column flex-md-row ga-3">
    <div class="d-flex flex-column process-width">
      <p class="project-title font-weight-bold mb-2">{{ projectDetail.name }}</p>
      <img
        :src="img_computed"
        alt="picture"
        class="mb-4 project-picture"
        v-if="projectDetail.project_image"
      />
      <img
        :src="default_img_computed"
        alt="picture-default"
        class="project-picture mb-4"
        v-else
      />
      <div class="mb-2">
        <span class="font-weight-bold pe-2">Link:</span>
        <a 
          :href="projectDetail.link" 
          target="_blank"
          v-if="projectDetail.link"
        >Here</a>
        <span v-else>-</span>
      </div>
      <div class="mb-2">
        <span class="font-weight-bold">Type:</span>
        <v-chip-group>
          <v-chip
            v-for="(type, typeIndex) in projectDetail.project_type"
            :key="typeIndex"
          >
            {{ type.name }}
          </v-chip>
        </v-chip-group>
      </div>
      <div class="mb-4">
        <span class="font-weight-bold">Tools:</span>
        <v-chip-group>
          <v-chip
            v-for="(tool, toolIndex) in projectDetail.project_tools"
            :key="toolIndex"
          >
            {{ tool.name }}
          </v-chip>
        </v-chip-group>
      </div>
      <p class="mb-4">{{ projectDetail.description }}</p>
    </div>
    <div class="mb-2 d-flex flex-column justify-md-end process-width">
      <p class="font-weight-bold">Process:</p>
      <ol class="ma-4">
        <li v-for="(pro, proIndex) in projectDetail.process" :key="proIndex">
          {{ pro.name }}
        </li>
      </ol>
      <p class="font-weight-bold">Key Findings:</p>
      <ol class="ma-4">
        <li
          v-for="(key, keyIndex) in projectDetail.key_findings"
          :key="keyIndex"
        >
          {{ key.name }}
        </li>
      </ol>
      <p class="font-weight-bold">Recommendation</p>
      <ul class="ma-4">
        <li
          v-for="(rec, recIndex) in projectDetail.recommendation"
          :key="recIndex"
        >
          {{ rec.name }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script setup lang="ts">
import { computed } from "vue";

const props = defineProps<{
  projectDetail: any;
}>();

const img_computed = computed(() => {
  return `../yonatie/src/assets/images/${props.projectDetail.project_image}`;
});

const default_img_computed = computed(() => {
  return `../yonatie/src/assets/images/img_placeholder.png`;
});
</script>

<style scoped lang="scss">
:deep() {
  .project-title {
    font-size: 28px;
  }

  .project-picture {
    max-width: 300px;
    border-radius: 8px;
  }

  .process-width {
    width: 100%;
  }

  @media (max-width: 960px) {


    ul li,
    ol li {
      line-height: 30px;
    }
  }

  @media (min-width: 961px) {
    .process-width {
      width: 50%;
    }
  }
}
</style>