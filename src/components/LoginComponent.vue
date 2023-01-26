<template>
  <v-container style="height: 100%">
    <v-row style="height: 85%">
      <v-col
        style="display: flex; align-items: center; justify-content: center"
      >
        <v-card
          style="
            display: grid;
            align-items: center;
            justify-content: center;
            text-align: center;
          "
        >
          <v-card-title style="text-align: center !important; display: grid"
            >Sua Loja</v-card-title
          >
          <v-card-subtitle>Realize seu login para acessar</v-card-subtitle>
          <v-card-text>
            <v-text-field v-model="email" solo label="Login"></v-text-field>
            <v-text-field
              v-model="password"
              :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
              :rules="[rules.required, rules.min]"
              :type="show1 ? 'text' : 'password'"
              solo
              hide-details
              label="Senha"
              @click:append="show1 = !show1"
            ></v-text-field>
          </v-card-text>
          <v-card-actions style="display: grid">
            <v-btn color="primary" class="ma-2">Entrar</v-btn>
            <p>
              Realize o <a href="">Registro</a><br /><a href=""
                >Recupere sua senha</a
              >
            </p>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "LoginComponent",
  data: () => ({
    email: "",
    password: "",
    show1: false,
    rules: {
      required: (value) => !!value || "Obrigatorio.",
      min: (v) => v.length >= 8 || "Minimo 8 caracteres",
      emailMatch: () => `Email e senha não coincidem`,
    },
  }),
};
</script>
