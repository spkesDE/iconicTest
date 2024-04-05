<script setup lang="ts">
import {IonIcon} from '@ionic/vue';
import {add, remove} from "ionicons/icons";

const props = defineProps({
  title: {
    type: String,
    required: true
  }
});
</script>

<template>
  <div style="margin-bottom: 15px">
    <ion-label position="fixed">{{ props.title }}</ion-label>
    <div style="float: right">
      <ion-toggle></ion-toggle>
    </div>
  </div>
</template>

<style scoped>

</style>