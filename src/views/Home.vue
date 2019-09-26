<template>
  <div class="ion-page">
    <ion-header>
      <ion-toolbar>
        <ion-title>Hello World</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content class="ion-padding">
      <h1>Welcome To @ionic/vue</h1>
      <img alt="Vue logo" src="../assets/logo.png">
      <ion-button @click="aboutPush()" full>Go to About Page</ion-button>
      <ion-button @click="showModal()" full>Go to Modal</ion-button>
    </ion-content>
  </div>
</template>

<script>
import Modal from '../components/Modal';

export default {
  name: "home",
  methods: {
    aboutPush() {
      this.$router.push('about')
    },
    showModal: async function() {
      const modal = await this.$ionic.modalController.create({
        component: Modal,
        componentProps: {
          data: {
            content: 'New Content',
          },
          propsData: {
            title: 'New title',
            msg: Math.round(Math.random() * 100)
          }
        }
      });
      await modal.present();
    }
  }
};
</script>