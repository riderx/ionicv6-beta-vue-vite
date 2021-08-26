<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-buttons slot="start">
          <ion-back-button></ion-back-button>
        </ion-buttons>
        <ion-title>Ionic Vite - About</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content class="ion-padding">
      <h1>About</h1>
      <!-- MODAL CODE -->
      <ion-modal :is-open="modalIsOpen" @didDismiss="closeModal()">
        <about-modal @onClose="closeModal" />
      </ion-modal>
      <ion-button @click="showModal">Open Modal</ion-button>
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
  import { onMounted, ref } from "vue";
  import {
    IonContent,
    IonButton,
    IonButtons,
    IonBackButton,
    IonPage,
    IonHeader,
    IonTitle,
    IonToolbar,
    IonModal,
    onIonViewWillEnter,
  } from "@ionic/vue";
  import AboutModal from "../components/AboutModal.vue";

  const modalIsOpen = ref(false);
  const showModal = () => {
    modalIsOpen.value = true;
  };

  const closeModal = () => {
    modalIsOpen.value = false;
  };

  onIonViewWillEnter(() => {
      console.log('onIonViewWillEnter test 1');
    });
    
  onMounted(() => {
    onIonViewWillEnter(() => {
      console.log('onIonViewWillEnter test 2');
    });
  });
</script>

<style>
</style>
