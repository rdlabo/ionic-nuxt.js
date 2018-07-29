<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>
          Ionic Blank
        </ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content>
      The world is your oyster.
      <p>If you get lost, the <a target="_blank" href="https://ionicframework.com/docs">docs</a> will be your guide.</p>

      <ion-button @click="presentToast">start Toast</ion-button>
    </ion-content>
    <ion-toast-controller></ion-toast-controller>
  </ion-page>
</template>

<script>
  export default {
    methods: {
      async presentToast() {
        const toastController = document.querySelector('ion-toast-controller');
        await toastController.componentOnReady();

        const toast = await toastController.create({
          message: 'Your settings have been saved.',
          duration: 200000
        });
        return await toast.present();
      }
    }
  }
</script>
