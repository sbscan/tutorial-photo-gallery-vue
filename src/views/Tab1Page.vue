<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Tab 1</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-button @click="setOpen(true)" id="present-alert">Click Me</ion-button>
  <ion-alert
  :is-open="isOpen"
    trigger="present-alert"
    header="Alert"
    sub-header="Important message"
    message="This is an alert!"
    :buttons="alertButtons"
    @didDismiss="setOpen(false)"
  ></ion-alert>
  </ion-page>
</template>

<script setup lang="ts">
import { IonAlert, IonButton, IonPage, IonHeader, IonToolbar, IonTitle } from '@ionic/vue';
import { ref } from 'vue';
const alertButtons = ['OK'];
const isOpen = ref(false);
 const setOpen = (state: boolean) => {
        isOpen.value = state;
      };
</script>

