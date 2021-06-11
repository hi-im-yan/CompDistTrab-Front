<template>
  <div>
    <Header @clicked="displayThisComponent"></Header>
    <Sobre v-if="selectedMenu == 'sobre'"></Sobre>
    <Integrantes v-if="selectedMenu == 'integrantes'"></Integrantes>
    <Carrinho></Carrinho>
  </div>
</template>

<script>
// @ is an alias to /src
import Header from '@/components/Header/Header.vue'
import Sobre from '@/components/Sobre/Sobre.vue'
import Integrantes from '@/components/Integrantes/Integrantes.vue'
import Carrinho from "../components/Carrinho/Carrinho";

export default {
  name: 'Home',

  data: () => ({
    selectedMenu: "",
    logged:false
  }),

  components: {
    Header,
    Sobre,
    Integrantes,
    Carrinho
  },

  methods: {
    displayThisComponent(value) {
      this.selectedMenu = value
    }
  }
}
</script>
