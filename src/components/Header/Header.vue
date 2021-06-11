<template>
  <div>

    <v-app-bar
        color="deep-purple"
        dark
    >
      <v-app-bar-nav-icon @click="drawer = true"></v-app-bar-nav-icon>

      <v-toolbar-title>
        <v-btn v-for="item in navbarItems" :key="item.nome" color="deep-purple" elevation="0" value="sobre" @click="displayThisComponent(item.nome)">
          {{ item.nome }}</v-btn>
      </v-toolbar-title>

    </v-app-bar>

    <v-navigation-drawer
        v-model="drawer"
        absolute
        temporary
    >
      <v-list
          nav

      >
        <v-list-item-group
            v-model="group"
            active-class="deep-purple--text text--accent-4"

        >
          <v-list-item @click="drawer = !drawer; displayThisComponent(item.nome)" v-for="item in drawerItems" :key="item.nome">
            <v-list-item-icon>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-item-icon>
            <v-list-item-title>{{ item.nome }}</v-list-item-title>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
  </div>

</template>

<script>
export default {
  name: "Header",

  data: () => ({
    drawer: false,
    group: null,
    drawerItems: [
      {"nome": "Home", "icon": "mdi-home"},
      {"nome": "Conta", "icon": "mdi-account"},
      {"nome": "Carrinho", "icon": "mdi-cart"},
    ],
    navbarItems: [
      {"nome": "sobre"},
      {"nome": "integrantes"},
      {"nome": "lojas"},
    ]
  }),

  methods: {
    displayThisComponent(value){
      this.$emit('clicked', value)
    }
  }
}
</script>

<style scoped>
h1 {
  color: black;
  text-align: center;
}
</style>