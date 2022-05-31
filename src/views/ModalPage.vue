<template>
  <ion-page>
    <ion-content>
      <ion-button v-on:click="openModal"> Open Modal </ion-button>
      <!-- Use a trigger -->
      <ion-button id="trigger-button">Click to open modal</ion-button>
      <ion-modal trigger="trigger-button" @didDismiss="handleModalDidDismiss"
        @didPresent="handleModalDidPresent">
        <ion-content>Modal Content - trigger button</ion-content>
      </ion-modal>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { IonContent, IonButton, IonPage, modalController, IonModal } from "@ionic/vue";
import { defineComponent } from "vue";
import ModalPageVue from "./ModalPage.vue";

export default defineComponent({
  name: "HomePage",
  components: {
    IonContent,
    IonButton,
    IonPage,
    IonModal
  },
  ionViewDidEnter() {
    console.log("This lifecycle hook works - HomePage:ionViewDidEnter");
  },
  methods: {
    handleModalDidDismiss() {
      console.log("trigger button - modal was dismissed...")
    },
    handleModalDidPresent() {
      console.log("trigger button - modal was presented...")
    },
    async openModal() {
      const modal = await modalController.create({
        component: ModalPageVue,
      });
      modal.onDidDismiss().then(() => {
        console.log("modal was dismissed...")
      });
      await modal.present().then(() => {
        console.log("modal was presented...")
      });
    },
  },
});
</script>

<style scoped>
</style>
