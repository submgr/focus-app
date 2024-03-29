<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>About App</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content>
      <ion-card style="border-radius: 20px;">
        <img src="/media/icon.png" style="width: 30vw; border-radius: 50%; margin-left: 5vw; margin-top: 4vh;"/>
        <ion-card-header>
          <ion-card-subtitle>Разработчик: Aram Virabyan</ion-card-subtitle>
          <ion-card-title>Focus! Pomodoro</ion-card-title>
        </ion-card-header>
        <ion-card-content>
          Иногда так сложно сконцентрироваться на работе, учебе, домашних делах... Приложение поможет вам сфокусироваться на задаче, а также предложит вам пресеты для разных сценариев.
        </ion-card-content>
      </ion-card>
      <ion-card style="border-radius: 20px;">
        <ion-card-header>
          <ion-card-subtitle>Попробуйте другое мое приложение — приложение для медитаций</ion-card-subtitle>
          <ion-card-title>Медитация!</ion-card-title>
        </ion-card-header>
        <ion-card-content>
          Иногда хочется расслабиться, отдохнуть, сконцентрироваться... в такие моменты хорошо подходит медитация. Обязательно попробуйте! Как минимум, это интересно.
        </ion-card-content>
      </ion-card>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent, IonCard, IonCardHeader, IonCardTitle, IonCardSubtitle, IonCardContent } from '@ionic/vue';

export default {
  components: { IonPage, IonHeader, IonToolbar, IonTitle, IonContent, IonCard, IonCardHeader, IonCardTitle, IonCardSubtitle, IonCardContent },
};
</script>