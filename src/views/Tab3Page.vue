<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Пресеты</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Пресеты</ion-title>
        </ion-toolbar>
      </ion-header>

      <div style="margin-top: 5vh; margin-left: 2vw; margin-right: 4vw;">
        <div v-for="(value, key) in presetsObject" :key="key" style="height: 10vh; background-color: var(--ion-card-background); margin-bottom: 2vh; border-radius: 20px;">
          <div style="margin-left: 4vw; padding-top: 3vw; ">
            <span style="font-size: 3vh;">{{ value.title }}</span><br/>
            <span style="font-size: 2vh; opacity: 0.7;">{{ value.description }}</span>
          </div>
        </div>
      </div>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent } from '@ionic/vue';
import ExploreContainer from '@/components/ExploreContainer.vue';


export default {
  components: { ExploreContainer, IonPage, IonHeader, IonToolbar, IonTitle, IonContent },
  setup() {
    // Return your object here so it can be used in the template
    const presetsObject = {
      key1: {
        title: "Рабочий день",
        description: "45 минут работы, 15 минут перерыв",
        time: 45,
        breaks: true
      },
      key2: {
        title: "Домашнее задание",
        description: "25 минут работы, 5 минут перерыв",
        time: 25,
        breaks: true
      },
      key3: {
        title: "Время для уборки",
        description: "30 минут уборки, 10 минут перерыв",
        time: 30,
        breaks: true
      },
      key4: {
        title: "Время для медитации",
        description: "20 минут медитации, без паузы на перерыв",
        time: 30,
        breaks: true
      },
      // add more key-value pairs as needed
    };
    return { presetsObject };
  },
};
</script>
