<template>
  <v-list-item two-line>
    <v-list-item-header>
      <v-list-item-title>{{ t("settings.rotate") }}</v-list-item-title>
      <v-slider
        hide-details
        density="compact"
        max="10"
        min="-10"
        thumb-label
        v-model="rotate_computed"
      />
    </v-list-item-header>
  </v-list-item>
</template>

<script lang="ts" setup>
import type { ScanConfig } from "@/utils/scan";
import { computed } from "vue";
import { useI18n } from "vue-i18n";
const { t } = useI18n();

type rotateType = ScanConfig["rotate"];

const props = defineProps<{
  rotate: rotateType;
}>();

const emit = defineEmits<{
  (e: "update:rotate", value: rotateType): void;
}>();

const rotate_computed = computed({
  get: () => props.rotate,
  set: (value) => emit("update:rotate", value),
});
</script>
