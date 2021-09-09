<template>
  <v-app>
    <v-app-bar app color="light-green">
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-toolbar-title>Rick & Morty characters</v-toolbar-title>

      <v-spacer></v-spacer>
    </v-app-bar>

    <v-navigation-drawer
      app
      v-model="drawer"
      color="lime"
      temporary
      :mobile-breakpoint="600"
    >
      <v-list dense nav>
        <v-list-item>
          <v-list-item-icon>
            <v-icon>mdi-home</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>Home</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        

          
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-container class="pt-16" >
      <v-row >
        <v-col cols="12"
        sm="6"
        lg="4" 
        class="pt-16"
        v-for="(personaje, id) in personajes" :key="id">
          <v-hover v-slot="{ hover }">
            <v-card
              v-ripple
              class="mx-auto card"
              max-width="344"
              :elevation="hover ? 12 : 2"
            >
              <v-img :src="personaje.imagen" height="200px"></v-img>

              <v-card-title> {{ personaje.nombre }}</v-card-title>
            </v-card>
          </v-hover>
        </v-col>
      </v-row>
    </v-container>
  </v-app>
</template>

<script>
export default {
  name: "App",

  data: () => ({
    drawer: false,
    personajes: [
      {
        id: 1,
        nombre: "Morty",
        imagen: "https://rickandmortyapi.com/api/character/avatar/2.jpeg",
      },
      {
        id: 2,
        nombre: "Rick",
        imagen: "https://rickandmortyapi.com/api/character/avatar/1.jpeg",
      },
      {
        id: 3,
        nombre: "Summer",
        imagen: "https://rickandmortyapi.com/api/character/avatar/3.jpeg",
      },
      {
        id: 4,
        nombre: "Beth",
        imagen: "https://rickandmortyapi.com/api/character/avatar/4.jpeg",
      },
      {
        id: 5,
        nombre: "Jerry",
        imagen: "https://rickandmortyapi.com/api/character/avatar/5.jpeg",
      },
    ],
  }),
};
</script>
<style >

</style>