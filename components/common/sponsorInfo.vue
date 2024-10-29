<template>
  <v-container fluid class="pa-0 ma-0">
    <v-row
      v-for="(item, index) in sponsorsData"
      :key="index"
      class="google-font mb-5 mt-0 justify-center"
    >
      <v-col md="12" cols="12" class="mb-n1">
        <h2 class="d-flex align-center justify-center">
          <img
            v-if="item.category_icon"
            :src="'/img/common/' + item.category_icon"
            width="50px"
            style="padding-top: 12px"
          />
          <span>
            {{ item.category_name }}
          </span>
          <img
            v-if="item.category_icon"
            :src="'/img/common/' + item.category_icon"
            width="50px"
            style="padding-top: 12px"
          />
        </h2>
      </v-col>
      <v-col
        cols="6"
        sm="4"
        md="3"
        class="text-center"
        style="min-height: 150px;"
        v-for="(sponsor, indexp) in item.sponsors"
        :key="indexp"
      >
        <div class="pa-5 sponsor-container">
          <ClientOnly>
            <v-tooltip location="bottom" :key="indexp">
              <template v-slot:activator="{ props }">
                <a
                  v-bind="props"
                  target="_blank"
                  class="w-100"
                  :href="sponsor.link"
                  :aria-label="sponsor.name"
                >
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