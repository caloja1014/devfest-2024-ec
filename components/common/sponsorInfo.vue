<template>
  <v-container fluid class="pa-0 ma-0">
    <v-row v-for="(item, index) in sponsorsData" :key="index" class="google-font mb-5 mt-0 justify-center">
      <v-col md="12" cols="12" class="mb-n1">
        <h2 class="d-flex align-center justify-center">
          <Award v-if="item.category_color" :pathColor="item.category_color" :circleColor="item.category_color" 
            :strokeWidth="0.6" />
          <span>
            {{ item.category_name }}
          </span>
          <Award v-if="item.category_color" :pathColor="item.category_color" :circleColor="item.category_color"
            :strokeWidth="0.6" />
        </h2>
      </v-col>
      <v-col cols="6" sm="4" md="3" class="text-center" style="min-height: 150px;"
        v-for="(sponsor, indexp) in item.sponsors" :key="indexp">
        <div class="pa-5 sponsor-container">
          <ClientOnly>
            <v-tooltip location="bottom" :key="indexp">
              <template v-slot:activator="{ props }">
                <a v-bind="props" target="_blank" class="w-100" :href="sponsor.link" :aria-label="sponsor.name">
                  <v-img alt="sponsor-logo" :src="'/img/sponsors/' + sponsor.logo"></v-img>
                </a>
              </template>
              <span>{{ sponsor.name }}</span>
            </v-tooltip>
          </ClientOnly>
        </div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
import Award from '~/components/icons/Award.vue';

const { sponsorsData } = useJSONData();
</script>

<style scoped>
  .sponsor-container {
    background-color: #F3F3F3;
    border-radius: 15px;
    border: 1.5px solid black;
    height: 100%;
    display: flex;
    align-items: center;
  }
</style>