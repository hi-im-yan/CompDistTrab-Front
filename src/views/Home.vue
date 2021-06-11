<template>
  <div>
    <Header @clicked="displayThisComponent"></Header>
    <Sobre v-if="selectedMenu == 'sobre'"></Sobre>
    <Integrantes v-if="selectedMenu == 'integrantes' || selectedMenu == ''"></Integrantes>
    <Lojas v-if="selectedMenu == 'lojas'" @clicked="displayThisLoja"></Lojas>
    <Produtos v-if="selectedLoja != -1 && selectedMenu == -1" v-bind:lojaId="selectedLoja" @clicked="addToCart"></Produtos>
  </div>
</template>

<script>
// @ is an alias to /src
import Header from '@/components/Header/Header.vue'
import Sobre from '@/components/Sobre/Sobre.vue'
import Integrantes from '@/components/Integrantes/Integrantes.vue'
import Lojas from '@/components/Lojas/Lojas.vue'
import Produtos from "../components/Produtos/Produtos";

export default {
  name: 'Home',

  data: () => ({
    selectedMenu: "",
    logged:false,
    selectedLoja: -1,
    cart: []
  }),

  components: {
    Header,
    Sobre,
    Integrantes,
    Lojas,
    Produtos
  },

  methods: {
    displayThisComponent(value) {
      this.selectedMenu = value
    },

    displayThisLoja(lojaId){
      this.selectedLoja = lojaId
      this.selectedMenu = -1
    },

    addToCart(productToAdd){
      this.cart.push(productToAdd)
    }
  }
}
</script>
