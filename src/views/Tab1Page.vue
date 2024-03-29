<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Фокусировка</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Фокусировка</ion-title>
        </ion-toolbar>
      </ion-header>

      
        
        

      <ion-card class="center-content" style="border-radius: 20px">
        <ion-grid class="center-content">
          <ion-row>
            <ion-col size="auto">
              <ion-input type="number" style="height: 17vh; width: 45vw; font-size: 10vh; text-align: center;" :value="timerValue" v-model="timerValue"></ion-input>
              <div class="center-content" style="margin-top: -4vh;">
                <p><ion-text>минут</ion-text></p>
                
              </div>
            </ion-col>
            <ion-col>
              <ion-button style="height: 8.5vh;" @click="timerUpdate('up')"><ion-icon slot="icon-only"  :icon="chevronUpOutline"></ion-icon></ion-button><br/>
              <ion-button style="height: 8.5vh;" @click="timerUpdate('down')"><ion-icon slot="icon-only"  :icon="chevronDownOutline"></ion-icon></ion-button>
            </ion-col>
          </ion-row>
        </ion-grid>
      </ion-card>

      <div class="center-content">
        <p v-if="!breaksDisabled && breaksAmount > 0"><ion-text>У вас будет {{ breaksAmount }} перерыв.</ion-text></p>
        <p v-else=><ion-text>Без пауз на перерывы.</ion-text></p>
        

        
      </div>

      <div class="center-content" style="width: 90vw !important; white-space: nowrap; margin-left: 20px; border-radius: 20px;">
        <ion-item style="border-radius: 20px;">
          <ion-label>Пропустить перерывы</ion-label>
          <ion-checkbox slot="start" :value="breaksDisabled" v-model="breaksDisabled"></ion-checkbox>
        </ion-item>
        

        
      </div>
      <div class="center-content" style="margin-top: 10px;">
        <ion-button style="margin-top: 2vh;">Начать фокусировку внимания <ion-icon slot="end" :icon="chevronForwardOutline"></ion-icon></ion-button>

        
      </div>

      <div class="center-content" style="opacity: 0.6;">
        <ion-button style="margin-top: 2vh;">Сохранить как пресет <ion-icon slot="end" :icon="fileTrayOutline"></ion-icon></ion-button>

        
      </div>
      

      
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent, IonButton, IonIcon, IonCheckbox } from '@ionic/vue';
import ExploreContainer from '@/components/ExploreContainer.vue';

import { chevronUpOutline, chevronDownOutline, chevronForwardOutline, fileTrayOutline } from 'ionicons/icons';

</script>

<script lang="ts">
  import { defineComponent } from 'vue';

  export default defineComponent({
    components: {  },
    data() {
      return {
        timerValue: 50,
        breaksDisabled: false,
        breaksAmount: 1
      };
    },
    methods: {
      timerUpdate: function (direction: string) {
        if (direction === 'up') {
          this.timerValue += 15;
        } else {
          this.timerValue -= 15;
        }
        if(this.timerValue < 10) {
          this.timerValue = 10;
        }
      },
    },
  });
</script>

<style scoped>
.center-content {
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
