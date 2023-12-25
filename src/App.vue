<script setup>
import Title from "./components/Title.vue";
import About from "./components/About.vue";
import ExperienceSkills from "./components/ExperienceSkills.vue";
import Projects from "./components/Projects.vue";
import { ref } from "vue";

const linkedList = ref([
  { icon: "mdi-linkedin", url: "https://www.linkedin.com/in/ynt29/" },
  { icon: "mdi-github", url: "https://github.com/ynt29/" },
  { icon: "mdi-email-outline", url: "yossakorntie@gmail.com", type: "email" },
  { icon: "mdi-cellphone" },
]);
</script>

<template>
  <div>
    <v-layout>
      <v-app-bar prominent :elevation="0" class="px-md-12">
        <v-spacer></v-spacer>
        <template
          v-for="(item, index) in linkedList"
          :key="index"
        >
          <v-btn icon
            v-if="!item.type"
            :href="item.url"
            target="_blank"
          >
            <v-icon class="text-white">{{ item.icon }}</v-icon>
          </v-btn>
          <a
            v-else
            :href="'mailto:'+item.url"
          >
            <v-btn icon>
              <v-icon class="text-white">{{ item.icon }}</v-icon>
            </v-btn>
          </a>
        </template>
      </v-app-bar>
      <v-main>
        <Title />
        <About />
        <ExperienceSkills />
        <Projects />
      </v-main>
    </v-layout>
  </div>
</template>

<style scoped lang="scss">
:deep() {
  .v-layout header {
    background: #0F4D92;
  }

  .v-btn:hover .v-btn__content i::before {
    color: #D3D3D3;
  }

  @media (min-width: 961px) {
    i {
      font-size: 32px;
    }
  }

}
</style>
