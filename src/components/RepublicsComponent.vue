<style>
.tab_all {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
  gap: 5%;
}
.like-btn {
  background-color: #8585857d;
}
@import url("https://fonts.googleapis.com/css2?family=Ubuntu&display=swap");
.font-ubunto {
  font-family: "Ubuntu", sans-serif;
}
.radius {
  border-radius: 10px;
}
</style>
<!-- eslint-disable  -->
<template>
  <v-container>
    <v-row>
      <v-col>
        <v-card
          style="
            display: grid;
            justify-content: center;
            align-items: center;
            width: 100%;
          "
        >
          <v-card-text class="pa-2">
            <v-text-field
              label="Pesquisar..."
              prepend-inner-icon="mdi-magnify"
              outlined
              hide-details
            >
            </v-text-field>
          </v-card-text>
        </v-card>
        <v-card class="pa-2 mt-3">
          <v-tabs v-model="tab" class="ma-1">
            <v-tab>Destaque</v-tab>
            <v-tab>Categorias</v-tab>
          </v-tabs>
          <v-tabs-items v-model="tab">
            <v-tab-item active-class="tab_all">
              <v-card
                width="45%"
                class="my-2"
                v-for="item in items"
                :key="item.i"
                @click="dialog = true"
              >
                <v-img class="radius" v-if="item.src == ''" :src="item.defaultImage">
                  <v-card-actions style="justify-content: flex-end;">
                    <v-btn
                      class="like-btn"
                      icon
                      color="success"
                      v-if="item.inCart == false"
                      @click.stop="item.inCart = true"
                    >
                      <v-icon>mdi-cart-plus</v-icon>
                    </v-btn>
                    <v-btn
                      class="like-btn"
                      icon
                      v-else
                      color="red"
                      @click.stop="item.inCart = false"
                    >
                      <v-icon>mdi-cart-minus</v-icon>
                    </v-btn>
                  </v-card-actions>
                </v-img>
                <v-img class="radius" v-else :src="item.src">
                  <v-card-actions style="justify-content: flex-end;">
                    <v-btn
                      class="like-btn"
                      icon
                      color="success"
                      v-if="item.inCart == false"
                      @click.stop="item.inCart = true"
                    >
                      <v-icon>mdi-cart-plus</v-icon>
                    </v-btn>
                    <v-btn
                      class="like-btn"
                      icon
                      v-else
                      color="red"
                      @click.stop="item.inCart = false"
                    >
                      <v-icon>mdi-cart-plus</v-icon>
                    </v-btn>
                  </v-card-actions>
                </v-img>
                <v-card-title class="font-ubunto">{{ item.title }}</v-card-title>
                <v-card-subtitle style="white-space: nowrap; overflow: hidden;text-overflow: ellipsis;">{{ item.subtitle }}</v-card-subtitle>
              </v-card>
            </v-tab-item>
          </v-tabs-items>
        </v-card>
      </v-col>
    </v-row>
    <v-dialog
      v-model="dialog"
      fullscreen
    >
      <v-card>
        <v-card-title class="text-h5 grey lighten-2">
          Privacy Policy
        </v-card-title>

        <v-card-text>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
        </v-card-text>

        <v-divider></v-divider>

        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn
            color="primary"
            text
            @click="dialog = false"
          >
            I accept
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-container>
</template>

<script>
/* eslint-disable */
export default {
  name: "RepublicsComponent",

  data: () => ({
    dialog: false,
    tab: null,
    items: [
      {
        i: 1,
        src: '',
        title: "Produto 1",
        defaultImage: require("../assets/default.png"),
        subtitle: "Product small description",
        inCart: false,
      },
      {
        i: 2,
        src: '',
        title: "Produto 2",
        defaultImage: require("../assets/default.png"),
        subtitle: "Product small description",
        inCart: false,
      },
      {
        i: 3,
        src: '',
        title: "Produto 3",
        defaultImage: require("../assets/default.png"),
        subtitle: "Product small description",
        inCart: false,
      },
      {
        i: 4,
        src: '',
        title: "Produto 4",
        defaultImage: require("../assets/default.png"),
        subtitle: "Product small description",
        inCart: false,
      },
    ],
  }),
  mounted() {
    console.log(this.tab);
  },
};
</script>
