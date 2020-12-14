<template>
  <v-app>
    <v-app-bar
      app
      color="indigo"
      dark
    >
      <v-app-bar-nav-icon></v-app-bar-nav-icon>
      <v-toolbar-title>oneWeek</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main>
      <HelloWorld/>
    </v-main>
  </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld';
import Home from "@/views/Home";

export default {
  name: 'App',

  components: {
    Home,
    HelloWorld,
  },

  data: () => ({
    //
  }),
};
</script>
