<template>
  <v-app id="inspire">
    <v-app-bar
        app
        shrink-on-scroll
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>

      <v-toolbar-title>{{ $t('homepage') }}</v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>mdi-dots-vertical</v-icon>
      </v-btn>
    </v-app-bar>

    <navigation :show="drawer"></navigation>

    <v-main>
      <router-view></router-view>
    </v-main>
  </v-app>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Navigation from './components/Navigation.vue';

export default defineComponent({
  name: "App",
  components: { Navigation },

  data() {
    return {
      drawer: false
    };
  },
});
</script>
