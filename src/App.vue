<template>
  <v-app>
    <Toolbar />

    <v-main>
      <Search v-on:searchResult="searchResult" />
      <Cards v-bind:items="items" />
    </v-main>
  </v-app>
</template>

<script>
import Toolbar from "./components/Toolbar";
import Search from "./components/Search";
import Cards from "./components/Cards";

export default {
  name: "App",

  components: {
    Toolbar,
    Search,
    Cards,
  },
  methods: {
    searchResult(response) {
      this.items = response;
    },
  },
  data() {
    return {
      items: [],
    };
  },
};
</script>