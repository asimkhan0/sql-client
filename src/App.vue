<template>
  <v-app>
    <v-app-bar
      absolute
      color="#43a047"
      dark
      shrink-on-scroll
      prominent
      src="https://picsum.photos/1920/1080?random"
      fade-img-on-scroll
      scroll-target="#scrolling-techniques-5"
      scroll-threshold="500"
    >
      <template v-slot:img="{ props }">
        <v-img
          v-bind="props"
          gradient="to top right, rgba(51,45,225,0.9051995798319328), rgba(45,160,225,1)"
        ></v-img>
      </template>

      <v-app-bar-nav-icon></v-app-bar-nav-icon>

      <v-app-bar-title>Atlan SQL Client</v-app-bar-title>

      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-heart</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-dots-vertical</v-icon>
      </v-btn>
    </v-app-bar>
    <div style="margin-top: 100px;">
        <v-main>
            <parser-container />
        </v-main>
    </div>
</v-app>
</template>

<script lang="ts">
import Vue from 'vue';
import Component from 'vue-class-component';
import ParserContainer from './components/ParserContainer.vue';

@Component({
  components: { ParserContainer },
})
export default class App extends Vue {}
</script>
<style>
html {
  overflow-y: auto !important;
}
</style>
