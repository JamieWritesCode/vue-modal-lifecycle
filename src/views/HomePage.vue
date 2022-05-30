<template>
  <ion-page>
    <ion-content>
      <ion-button v-on:click="openModal"> Open Modal </ion-button>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { IonContent, IonButton, IonPage, modalController } from "@ionic/vue";
import { defineComponent } from "vue";
import ModalPageVue from "./ModalPage.vue";

export default defineComponent({
  name: "HomePage",
  components: {
    IonContent,
    IonButton,
    IonPage,
  },
  ionViewDidEnter() {
    console.log("This lifecycle hook works");
  },
  methods: {
    async openModal() {
      const modal = await modalController.create({
        component: ModalPageVue,
      });
      await modal.present();
    },
  },
});
</script>

<style scoped></style>
