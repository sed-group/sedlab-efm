<template>
  <v-app>
    <v-app-bar
      app
      dark
    >
      <v-img
        class="mx-2"
        src="favicon.png"
        max-height="40"
        max-width="40"
        contain
      ></v-img>
      <v-toolbar-title class="headline text-uppercase">
        <span>SED</span>
        <span class="font-weight-light">Lab EF-M</span>
      </v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn
        href="https://systemsengineering.design/"
        target="_blank"
        text
      >
        <span class="mr-2">SEDLab</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
      <v-btn
        @click="overlay = !overlay"
        text
      >
        <span class="mr-2">Sign In</span>
        <v-icon>mdi-account</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main>
      <Main/>
    </v-main>
    <v-overlay :value="overlay">
      <v-card
        class="ma-2 pa-4"
        width="344"
        light
      >
        <v-form v-model="valid">
          <v-container>
            <v-row>
              <h1>Work In Progress</h1>
            </v-row>
            <v-row>
              <v-text-field
                v-model="email"
                label="E-mail"
                required
              ></v-text-field>
            </v-row>
            <v-row>
              <v-text-field
                v-model="password"
                label="password"
                required
                :type="show1 ? 'text' : 'password'"
              ></v-text-field>
            </v-row>
          </v-container>
        </v-form>
        <v-btn
          color="error"
          @click="overlay = false"
        >
          Close
        </v-btn>
      </v-card>
    </v-overlay>
  </v-app>
</template>

<script>
import Main from './components/Main';

export default {
  name: 'App',

  components: {
    Main,
  },

  data: () => ({
    //
    overlay: false,
    email: null,
    password: null,
  }),
};
</script>
