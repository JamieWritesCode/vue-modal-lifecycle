<template>
  <ion-page>
    <ion-content>
      <p>This is a modal</p>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { IonContent, IonPage } from "@ionic/vue";
import { defineComponent } from "vue";

export default defineComponent({
  name: "ModalPage",
  components: {
    IonContent,
    IonPage,
  },
  ionViewDidEnter() {
    console.log("This lifecycle hook should also work, but doesn't");
  },
});
</script>

<style scoped></style>
