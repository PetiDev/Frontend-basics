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

    <v-toolbar dense color="accent">
      <v-btn icon dark @click.stop="drawer = !drawer">
        <v-icon color="primary">mdi-menu</v-icon>
      </v-btn>

      <v-toolbar-title class="primary--text" style="cursor: pointer" @click="$router.push('/')">
        Frontend alapok
      </v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn @click="changeClr()" icon>
        <v-icon color="primary">
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
        icon: "mdi-home",
        title: "temp1",
        target: "/",
      },
      {
        icon: "mdi-home",
        title: "temp2",
        target: "/",
      },
      {
        icon: "mdi-home",
        title: "temp3",
        target: "/inspire",
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
span{
  text-align: center;
}
h1, h2{
  
  margin-top: 1rem;
}
</style>
