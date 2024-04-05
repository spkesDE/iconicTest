<script setup lang="ts">
import {IonPage, IonHeader, IonToolbar, IonTitle, IonContent, IonIcon} from '@ionic/vue';
import {add, remove} from "ionicons/icons";
import SliderComp from "@/components/SliderComp.vue";
import ToggleComp from "@/components/ToggleComp.vue";

const props = withDefaults(defineProps<{
  type: string;
  id: string;
  name: string;
  found: boolean;
}>(), {
  type: 'mMTW',
  id: 'defaultId',
  name: 'Unknown Device',
  found: false,
});



</script>

<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>{{ props.name }}</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-card>
        <ion-card-header>
          <ion-card-title>General</ion-card-title>
        </ion-card-header>
        <ion-card-content>
          <ToggleComp title="FCMode" />
          <ToggleComp title="CBMode" />
          <SliderComp title="Magazine Counter" :max="400" />
          <SliderComp title="Friction Timer" :max="99" />
          <SliderComp title="Friction Value" :max="99" />
          <SliderComp title="Sniper Delay" :max="6" :steps="true" />
        </ion-card-content>
      </ion-card>

      <ion-card>
        <ion-card-header>
          <ion-card-title>Semi</ion-card-title>
        </ion-card-header>
        <ion-card-content>
          <SliderComp title="BB to Fire" :max="99" />
          <SliderComp title="Poppet Dwell" :max="255" />
          <SliderComp title="Nozzle Dwell" :max="255" />
          <SliderComp title="Poppet Delay" :max="255" />
        </ion-card-content>
      </ion-card>

      <ion-card>
        <ion-card-header>
          <ion-card-title>Auto</ion-card-title>
        </ion-card-header>
        <ion-card-content>
          <SliderComp title="BB to Fire" :max="99" />
          <SliderComp title="Poppet Dwell" :max="255" />
          <SliderComp title="Nozzle Dwell" :max="255" />
          <SliderComp title="Poppet Delay" :max="255" />
        </ion-card-content>
      </ion-card>
    </ion-content>
  </ion-page>
</template>

<style>
.label-text-wrapper {
  margin-bottom: 0 !important;
}
</style>

