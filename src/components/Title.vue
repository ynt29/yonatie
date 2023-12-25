<template>
  <div 
    class="d-flex flex-column w-full text-white pa-4 pa-md-12"
    >
    <article
      class="d-flex flex-column flex-md-row align-start align-md-center mb-7"
    >
      <div class="w-100 d-flex flex-column">
        <span class="hello">Hi, I'm</span>
        <h1 class="name-title">Yossakorn Napeang</h1>
        <p class="mb-2 description">
          A Junior Frontend Developer from Bangkok, Thailand.
          <br />
          with a passionate interest in the world of data analytics.
        </p>
      </div>
      <img :src="mypic_computed" alt="mypic" class="mypic mb-2" />
      <!-- <img :src="default_img_computed" alt="mypic" class="mypic mb-2" /> -->
    </article>
  </div>
</template>

<script setup>
import { ref, computed } from "vue";

const fadeContainer = ref();

const mypic_computed = computed(() => {
  return `yonatie/src/assets/images/mypic.png`;
});

const default_img_computed = computed(() => {
  return `yonatie/src/assets/images/img_placeholder.png`;
});

</script>

<style scoped lang="scss">
:deep() {
    .hello {
        font-size: 28px;
    }

    .description {
      font-size: 20px;
    }

    .name-title {
        font-size: 34px;
    }

    .mypic {
        object-fit: cover;
        border-radius: 8px;
        height: 100%;
        width: 100%;
        border-radius: 8px;
    }

    @media (max-width: 960px) {
      .mypic {
        max-height: 380px;
        max-width: 320px;
      }
    }

    @media (min-width: 961px) {
    .mypic {
      width: 480px !important;
    }

    .hello {
      font-size: 48px;
    }

    .name-title {
      font-size: 72px;
    }

    .description {
      font-size: 28px;
    }

  }
}

</style>