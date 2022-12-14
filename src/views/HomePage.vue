<template>
  <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-row>
            <ion-col>
                <ion-title>App logo</ion-title>
            </ion-col>
            <ion-col>
              <ion-title>HomePage</ion-title>
            </ion-col>
            <ion-col size="auto">
              <ButtonLink link="about" label="Go About" />
            </ion-col>
          </ion-row>
      </ion-toolbar>
    </ion-header>
    
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Blank</ion-title>
        </ion-toolbar>
      </ion-header>
    
      <div id="container">
        <strong>Ready to create an app?</strong>
        <p>Start with Ionic <a target="_blank" rel="noopener noreferrer" href="https://ionicframework.com/docs/components">UI Components</a></p>
        <p v-if="state.plateform.includes('mobile')">Vous êtes sur un mobile</p>
        <p v-else>Vous êtes sur un ordi</p>
      <ion-grid v-for="(personn, key) in personns" :key="key">
        <ion-row>
          <ion-col>
            <FirstComponents :name="personn.name" :age="personn.age" />
          </ion-col>
        </ion-row>
      </ion-grid>
      </div>
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonCol, IonGrid, IonRow } from '@ionic/vue';
import FirstComponents from '@/components/FirstComponents.vue';
import ButtonLink from '@/components/ButtonLink.vue';
import { getPlatforms } from '@ionic/vue';
import { watchEffect, computed, reactive } from 'vue';


const plateform  = computed(() => {
  return getPlatforms();
});

const state = reactive<
  {
    plateform: ("mobile" | "ios" | "ipad" | "iphone" | "android" | "phablet" | "tablet" | "cordova" | "capacitor" | "electron" | "pwa" | "mobileweb" | "desktop" | "hybrid")[];
    isMobile: boolean;
    personns: {
      name: string;
      age: number;
    }[];
  }
>(
  {
    plateform: plateform.value,
    isMobile: false,
    personns: [
      {
        name: 'John',
        age: 20
      },
      {
        name: 'Jane',
        age: 21
      },
      {
        name: 'Jack',
        age: 22
      }
    ]
  }
);

const personns = [
  {
    name: 'John',
    age: 20
  },
  {
    name: 'Jane',
    age: 21
  },
  {
    name: 'Jack',
    age: 22
  }
];

</script>

<style scoped>
#container {
  text-align: center;
  
  position: absolute;
  left: 0;
  right: 0;
  top: 50%;
  transform: translateY(-50%);
}

#container strong {
  font-size: 20px;
  line-height: 26px;
}

#container p {
  font-size: 16px;
  line-height: 22px;
  
  color: #8c8c8c;
  
  margin: 0;
}

#container a {
  text-decoration: none;
}
</style>
