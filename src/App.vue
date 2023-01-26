<template>
  <v-app>
    <v-main>
      <v-toolbar
        style="
          display: flex;
          justify-content: start;
          align-items: center;
          width: 100%;
        "
        text
        height="50px"
      >
        <v-switch
          v-model="$vuetify.theme.dark"
          inset
          :append-icon="
            $vuetify.theme.dark == false
              ? 'mdi-weather-night'
              : 'mdi-weather-sunny'
          "
          hide-details
        ></v-switch>
        <div
          style="
            display: inherit;
            justify-content: end;
            align-items: center;
            width: 15rem;
          "
        >
          <v-btn icon color="primary">
            <v-icon>mdi-cart-outline</v-icon>
          </v-btn>
        </div>
      </v-toolbar>
      <router-view />
    </v-main>
    <v-bottom-navigation :value="value" color="primary" fixed>
      <v-btn text icon>
        <span>Republicas</span>

        <v-icon>mdi-home-city-outline</v-icon>
      </v-btn>

      <v-btn text icon>
        <span>Eventos</span>

        <v-icon>mdi-calendar-check-outline</v-icon>
      </v-btn>

      <v-btn text icon>
        <span>Alunos</span>

        <v-icon>mdi-account-group-outline</v-icon>
      </v-btn>
    </v-bottom-navigation>
  </v-app>
</template>

<script>
export default {
  name: "App",

  data: () => ({
    value: "",
  }),
};
</script>
