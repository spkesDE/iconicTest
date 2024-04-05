<script setup lang="ts">
import { IonIcon } from '@ionic/vue';
import {add, remove} from "ionicons/icons";

const props = defineProps({
  min: {
    type: Number,
    default: 0
  },
  max: {
    type: Number,
    default: 100
  },
  title: {
    type: String,
    required: true
  },
  steps: {
    type: Boolean,
    default: false
  }
});
</script>

<template>
  <ion-label position="fixed">{{ props.title }}</ion-label>
  <ion-range :min="props.min" :max="props.max" :pin="true" style="padding-top: 0" :snaps="props.steps" :ticks="props.steps">
    <ion-icon slot="start" size="small" :icon="remove" />
    <ion-icon slot="end" size="small" :icon="add" />
  </ion-range>
</template>

<style scoped>

</style>