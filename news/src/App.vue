<template>
  <v-app>
    <AppBar v-on:appbar-click="changeNav()"></AppBar>
    <v-navigation-drawer app v-model="navigation" absolute temporary>
      <NavDrawer></NavDrawer>
    </v-navigation-drawer>

    <v-main>
      <v-content app>
        <v-container class="lighten-5 mb-6">
          <v-row no-gutters style="height: 150px">
            <v-col v-for="card in ListNews" :key="card">
              <slot>
                <CardNews :title="card['title']" :source_url="card['url']" :img_url="card['urlToImage']></CardNews>
              </slot>
              
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
    ListNews: [],
  }),

  methods: {
    changeNav() {
      this.navigation = !this.navigation;
      console.log(this.navigation);
    },
    getListNews() {
      this.axios.get("https://newsapi.org/v2/top-headlines?country=ru&apiKey=d7f41a32c26b4bbfb596d58b1a54c766").then((response) => {
        this.ListNews = response['data']['articles'];
        console.log(this.ListNews);
        //console.log(response['data']['articles']['0']['title']);
        //response['data']['articles']['0']['source']['author']
      });
    },
  },

  mounted(){
    this.getListNews();
  }
};
</script>
