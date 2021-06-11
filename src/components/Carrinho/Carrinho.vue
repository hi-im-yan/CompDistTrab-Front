<template>
<v-container class="mt-5">
  <v-data-table
      :headers="headers"
      :items="produtos"
      :items-per-page="5"
      item-key="name"
      class="elevation-1"
      :footer-props="{
      showFirstLastPage: true,
      firstIcon: 'mdi-arrow-collapse-left',
      lastIcon: 'mdi-arrow-collapse-right',
      prevIcon: 'mdi-minus',
      nextIcon: 'mdi-plus'
    }"
  ></v-data-table>
  <v-divider class="mt-5"></v-divider>
  <v-row>
    <v-col
      cols="2"
    >
      <v-text-field
          placeholder="Valor Total"
          disabled
          v-model="valorTotalReaisString"
      >
      </v-text-field>
    </v-col>
    <v-col
      cols="1"
    >
      <v-btn
          outlined
          class="mt-5"
          color="deep-purple lighten-2"
          @click="snackbar = true"
      >
        confirmar compra
        <v-icon right>
          mdi-cart-check
        </v-icon>
      </v-btn>
    </v-col>
  </v-row>
  <v-snackbar
      v-model="snackbar"
      :timeout="timeout"
  >
    Pedido efetuado

    <template v-slot:action="{ attrs }">
      <v-btn
          color="blue"
          text
          v-bind="attrs"
          @click="snackbar = false"
      >
        Close
      </v-btn>
    </template>
  </v-snackbar>
</v-container>
</template>

<script>
export default {
  name: "Carrinho",

  props: ['cart'],

  watch: {
    cart: {
      immediate: true,
      handler(val){
        this.produtos = val
        this.produtos.forEach((produto) => {
          this.valorTotalReais += produto.totalPrice
          this.valorTotalReaisString = "R$ " + this.valorTotalReais
        })
      }
    }
  },

  data () {
    return {
      snackbar: false,
      timeout: 2000,
      valorTotalReaisString: "R$ 0",
      valorTotalReais: 0,
      headers: [
        {
          text: 'Produto',
          align: 'start',
          value: 'productName',
        },
        { text: 'Quantidade', value: 'quantity' },
        { text: 'Preço', value: 'totalPrice' },
      ],
      produtos: [],
    }
  },
}
</script>

<style scoped>

</style>