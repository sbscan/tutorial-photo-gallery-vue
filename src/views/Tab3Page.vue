<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Tab 3</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
        <ion-accordion-group>
      <ion-accordion value="first">
        <ion-item slot="header" color="light">
          <ion-label>Device ID</ion-label>
        </ion-item>
        <div class="ion-padding" slot="content">
          {{ devId }}
        </div>
      </ion-accordion>
      <ion-accordion value="second">
        <ion-item slot="header" color="light">
          <ion-label>Device Info</ion-label>
        </ion-item>
        <div class="ion-padding" slot="content">
          {{ devInfo }}
        </div>
      </ion-accordion>
      <ion-accordion value="third">
        <ion-item slot="header" color="light">
          <ion-label>Batery Info</ion-label>
        </ion-item>
        <div class="ion-padding" slot="content">
         {{ battInfo }}
        </div>
      </ion-accordion>
    </ion-accordion-group>
</ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import { IonAccordion, 
    IonAccordionGroup,
    IonItem, 
  IonLabel, IonPage, IonHeader, IonToolbar, IonTitle, IonContent
} from '@ionic/vue';
import { Device } from '@capacitor/device';
const devId = ref();
const devInfo = ref();
const battInfo = ref();
getInfo();

async function getInfo () {
  devId.value = await Device.getId();
  devInfo.value = await Device.getInfo();
  battInfo.value = await Device.getBatteryInfo();
}
</script>
