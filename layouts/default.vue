<template>
  <v-app>
    <v-navigation-drawer v-model="drawer" absolute temporary>
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title>HTML alapok</v-list-item-title>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list dense>
        <v-list-item
          v-for="item in items"
          v-bind:key="item.title"
          :to="item.target"
          link
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-toolbar dense color="primary">
      <v-btn icon dark @click.stop="drawer = !drawer">
        <v-icon color="accent">mdi-menu</v-icon>
      </v-btn>

      <v-toolbar-title class="accent--text" style="cursor: pointer" @click="$router.push('/')">
        Frontend alapok
      </v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn @click="changeClr()" icon>
        <v-icon color="accent">
          {{
            currentColor == "light"
              ? "mdi-moon-waxing-crescent"
              : "mdi-white-balance-sunny"
          }}
        </v-icon>
      </v-btn>
    </v-toolbar>

    <Nuxt />
  </v-app>
</template>

<script>
export default {
  name: "DefaultLayout",

  data: () => ({
    currentColor: "dark",
    drawer: null,
    items: [
      {
        icon: "mdi-home",
        title: "Főoldal",
        target: "/",
      },
      {
        icon: "mdi-file-question",
        title: "Bevezetés",
        target: "/intro",
      },
      {
        icon: "mdi-roman-numeral-1",
        title: "A kezdetek",
        target: "/html/intro",
      },
      {
        icon: "mdi-roman-numeral-2",
        title: "Gyakori HTML elemek",
        target: "/html/basic",
      },
      {
        icon: "mdi-roman-numeral-3",
        title: "Inputok",
        target: "/html/inputs",
      },
      {
        icon: "mdi-roman-numeral-1",
        title: "CSS",
        target: "/css/intro",
      },
      {
        icon: "mdi-roman-numeral-2",
        title: "Formázások",
        target: "/css/basic",
      },
    ],
  }),
  methods: {
    changeClr() {
      if (this.currentColor == "dark") {
        this.$vuetify.theme.dark = false;
        this.currentColor = "light";
      } else {
        this.$vuetify.theme.dark = true;
        this.currentColor = "dark";
      }
    },
  },
};
</script>

<style>
.v-toolbar {
  flex: 0 1 auto !important;
}

span, h1, h2{
  text-align: center;
}
h1, h2{
  
  margin-top: 1rem;
}
section{
  position: relative;
}
section::after{
  content: "";
  width: 100%;
  height: 3px;
  background-color: #ff4757;
  position: absolute;
  bottom: -5px;
  left: 0;
}
code{
    color: #ffffff !important;
    background-color: #2a2a2a !important;
    text-align: left;
}
</style>
