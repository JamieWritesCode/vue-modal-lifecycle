<template>
  <ion-page>
    <ion-content>
      <p>This is a modal</p>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { IonContent, IonPage, onIonViewDidEnter, onIonViewDidLeave, onIonViewWillEnter, onIonViewWillLeave } from "@ionic/vue";
import { defineComponent, onMounted, onUnmounted } from "vue";

export default defineComponent({
  name: "ModalPage",
  components: {
    IonContent,
    IonPage,
  },
  setup(props) {
    onMounted(() => {
      console.log("modal mounted")
    });
    onUnmounted(() => {
      console.log("modal unmounted")
    });
  }
});
</script>

<style scoped>
</style>
