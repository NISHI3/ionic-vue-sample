<template>
  <div>
    <ion-header>
        <ion-toolbar>
            <ion-title>{{ title }} </ion-title>
        </ion-toolbar>
    </ion-header>
    <ion-content padding>
        {{ content }}
        {{ msg }}<br>
        <ion-button @click="dissmissModal()" full>bask to Modal</ion-button>
    </ion-content>
  </div>
</template>

<script>
export default {
    name: 'Modal',
    props: {
        title: { type: String, default: 'Super Modal'},
        msg: { type: Number, default: 0},
    },
    data() {
        return {
            content: "Content"
        }
    },
    methods: {
        dissmissModal() {
            this.$ionic.modalController.dismiss();
        }
    }
}
</script>

<style>

</style>