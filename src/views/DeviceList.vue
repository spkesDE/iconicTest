<script setup lang="ts">
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent, IonIcon } from '@ionic/vue';
import {arrowForward} from "ionicons/icons";
import {onMounted} from "vue";

// FCU Types -> mMTW, mFCU, FCU
const devices = [
  { name: 'Gorilla mFCU', id: 'afsr55213123', type: "mFCU", found: false },
  { name: 'hide my fcu', id: 'afsr55213123', type: "mMTW", found: true },
  { name: 'Gorilla FCU', id: 'afsr55213123', type: "FCU", found: false },
];

onMounted(() => {
  //Sort devices if found
  devices.sort((a, b) => {
    if (a.found && !b.found) return -1;
    if (!a.found && b.found) return 1;
    return 0;
  });
});
</script>

<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Gorilla FCU</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-card v-for="device in devices" :key="device.id">
        <ion-card-header>
          <ion-card-title>{{ device.name }}</ion-card-title>
          <ion-card-subtitle>{{device.type}} - {{ device.id }}</ion-card-subtitle>
        </ion-card-header>

        <ion-card-content v-if="device.found">
          <ion-button expand="full" shape="round" fill="outline">
            Connect <ion-icon :icon="arrowForward" />
          </ion-button>
        </ion-card-content>
      </ion-card>
    </ion-content>
  </ion-page>
</template>
