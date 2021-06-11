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

  data () {
    return {
      snackbar: false,
      timeout: 2000,
      headers: [
        {
          text: 'Produto',
          align: 'start',
          value: 'name',
        },
        { text: 'Quantidade', value: 'quantidade' },
        { text: 'Preço total', value: 'preco' },
      ],
      produtos: [
        {
          name: 'Frozen Yogurt',
          quantidade: 1,
          preco: 'Ice cream',
        },
        {
          name: 'Ice cream sandwich',
          quantidade: 1,
          preco: 'Ice cream',
        },
        {
          name: 'Eclair',
          quantidade: 1,
          preco: 'Cookie',
        },
        {
          name: 'Cupcake',
          quantidade: 1,
          preco: 'Pastry',
        },
        {
          name: 'Gingerbread',
          quantidade: 1,
          preco: 'Cookie',
        },
        {
          name: 'Jelly bean',
          quantidade: 1,
          preco: 'Candy',
        },
        {
          name: 'Lollipop',
          quantidade: 1,
          preco: 'Candy',
        },
        {
          name: 'Honeycomb',
          quantidade: 1,
          preco: 'Toffee',
        },
        {
          name: 'Donut',
          quantidade: 1,
          preco: 'Pastry',
        },
        {
          name: 'KitKat',
          quantidade: 1,
          preco: 'Candy',
        },
      ],
    }
  },
}
</script>

<style scoped>

</style>