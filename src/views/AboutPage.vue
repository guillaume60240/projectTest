<template>
    <ion-page>
      <ion-header :translucent="true">
        <ion-toolbar>
          <ion-row>
            <ion-col>
                <ion-title>App Name and logo</ion-title>
            </ion-col>
            <ion-col>
              <ion-title>AboutPage</ion-title>
            </ion-col>
            <ion-col size="auto">
              <ButtonLink link="home" label="Go Home" />
            </ion-col>
          </ion-row>
        </ion-toolbar>
      </ion-header>
      
      <ion-content :fullscreen="true">
        <ion-header collapse="condense">
          <ion-toolbar>
            <ion-title size="large">This is the about page</ion-title>
          </ion-toolbar>
        </ion-header>
      
        <div id="container">
          <strong>Why not?</strong>
          <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit vel pariatur ipsa reprehenderit, sapiente quaerat error ad quas reiciendis praesentium repellat repudiandae nemo dignissimos aspernatur. Totam voluptates maiores laborum praesentium.</p>
        </div>
      </ion-content>
    </ion-page>
</template>
  
<script setup lang="ts">
  import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonRow, IonCol } from '@ionic/vue';
  import ButtonLink from '@/components/ButtonLink.vue';
  
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