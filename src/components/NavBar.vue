<template>
  <v-app-bar elevation="4">
    <v-app-bar-title tag="h1">
      <router-link :to="{ name: 'index' }" class="nav-link">
        {{ t("base.title") }}
      </router-link>
    </v-app-bar-title>

    <template v-slot:append>
      <v-btn
        :href="HOMEPAGE_URL"
        @click.prevent="openHomepage"
        :icon="mdiHome"
      />
      <v-btn :href="GITHUB_URL" @click.prevent="openGitHub" :icon="mdiGithub" />
    </template>
  </v-app-bar>
</template>

<script setup lang="ts">
import { mdiGithub, mdiHome } from "@mdi/js";
import { useI18n } from "vue-i18n";
const { t } = useI18n();

const GITHUB_URL = "https://github.com/rwv/lookscanned.io";

const openGitHub = () => window.open(GITHUB_URL, "_blank");

const HOMEPAGE_URL = "https://zczc.cz/";

const openHomepage = () => window.open(HOMEPAGE_URL, "_blank");
</script>

<style lang="scss" scoped>
.nav-link {
  text-decoration: none;
  color: inherit;

  &:hover {
    text-decoration: none;
  }
}
</style>
