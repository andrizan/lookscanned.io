<template>
  <v-container>
    <v-row no-gutters class="text-center">
      <v-col cols="12" class="mb-4 middle">
        <div style="max-width: 12rem">
          <img :src="IconUrl" style="width: 100%" />
        </div>

        <h1 class="v-heading text-h3 text-sm-h3 mb-4">{{ t("base.title") }}</h1>
        <p class="mx-auto text-justify mb-8" style="max-width: 568px">
          {{ t("base.description") }}
        </p>

        <div>
          <v-btn class="mr-2" :to="{ name: 'scan' }">
            {{ t("actions.navigateToScan") }}
          </v-btn>
          <v-btn class="ml-2" :href="GITHUB_URL" @click.prevent="openGitHub"
            >GitHub</v-btn
          >
        </div>
      </v-col>

      <v-col cols="12" class="text-center mt-10">
        <v-row>
          <FeaturePrivacy />
          <FeatureSpeed />
          <FeatureCustomization />
          <FeatureOpenSource />
          <FeatureMobileFriendly />
          <FeatureOfflineUse />
        </v-row>
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup lang="ts">
import FeaturePrivacy from "@/components/Features/FeaturePrivacy.vue";
import FeatureSpeed from "@/components/Features/FeatureSpeed.vue";
import FeatureCustomization from "@/components/Features/FeatureCustomization.vue";
import FeatureOpenSource from "@/components/Features/FeatureOpenSource.vue";
import FeatureMobileFriendly from "@/components/Features/FeatureMobileFriendly.vue";
import FeatureOfflineUse from "@/components/Features/FeatureOfflineUse.vue";

import IconUrl from "@/assets/scanner.svg";
import { useI18n } from "vue-i18n";
const { t } = useI18n();

const GITHUB_URL = "https://github.com/rwv/lookscanned.io";

const openGitHub = () => window.open(GITHUB_URL, "_blank");
</script>

<style scoped>
.middle {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.advantage-icon {
  font-size: 8em;
}
</style>

<style lang="scss" scoped>
.plain-link {
  text-decoration: none;
  color: inherit;

  &:hover {
    text-decoration: none;
  }
}
</style>
