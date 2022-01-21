<template>
  <v-app>
    <AppBar v-on:appbar-click="changeNav()"></AppBar>
    <v-navigation-drawer app v-model="navigation" absolute temporary>
      <NavDrawer></NavDrawer>
    </v-navigation-drawer>

    <v-main>
      <v-content app>
        <v-container
          class="lighten-5 mb-6"
        >
          <v-row no-gutters style="height: 150px">
            <v-col v-for="n in 3" :key="n">
              <CardNews></CardNews>
            </v-col>
          </v-row>
        </v-container>
      </v-content>
    </v-main>
  </v-app>
</template>

<script>
//import HelloWorld from './components/HelloWorld';
import AppBar from "./components/AppBar";
import CardNews from "./components/CardNews";
import NavDrawer from "./components/NavDrawer";

export default {
  name: "App",

  components: {
    AppBar,
    CardNews,
    NavDrawer,
  },

  data: () => ({
    navigation: false,
  }),

  methods: {
    changeNav() {
      this.navigation = !this.navigation;
      console.log(this.navigation);
    },
  },
};
</script>
