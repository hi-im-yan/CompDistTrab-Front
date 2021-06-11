<template>
  <v-row>
    <v-card
        v-for="produto in displayThisProducts" :key="produto.nome"
        class="mx-auto my-12"
        min-width="374"
        max-width="374"
    >
      <v-img
          height="350"
          v-bind:src="produto.picture"
      ></v-img>

      <v-card-title>{{ produto.nome }}</v-card-title>



      <v-card-text>
        <v-row
            align="center"
            class="mx-0"
        >

        <div class="my-4 text-subtitle-1">
          Em estoque: {{ produto.emEstoque }}
          <br>
          Preço: {{ produto.preco }}
        </div>
        </v-row>
      </v-card-text>

      <v-divider class="mx-4"></v-divider>


      <v-card-actions>
        <v-text-field
            v-model="produto.qtdProduto"
            color="deep-purple lighten-2"
            class="ml-5"
            placeholder="quantidade"
            type="number"
            min="0"
        ></v-text-field>
        <v-btn
            class="ma-2"
            filled
            color="deep-purple lighten-2"
            dark
            @click="snackbar = true; addToCart(produto.nome, produto.preco, produto.qtdProduto)"
        >
          Adicionar
          <v-icon
              right
          >
            mdi-cart
          </v-icon>
        </v-btn>
        <v-snackbar
          v-model="snackbar"
          :timeout="timeout"
      >
        Adicionado ao carrinho

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

      </v-card-actions>
    </v-card>
  </v-row>
</template>

<script>
export default {
  name: "Produtos",

  props: ['lojaId'],

  watch: {
    lojaId: {
      immediate: true,
      handler(val){
        switch(val) {
          case 1:
            this.displayThisProducts = this.produtosLojaId_1
            break
          case 2:
            this.displayThisProducts = this.produtosLojaId_2
            break
          case 3:
            this.displayThisProducts = this.produtosLojaId_3
            break
          case 4:
            this.displayThisProducts = this.produtosLojaId_4
            break
          case 5:
            this.displayThisProducts = this.produtosLojaId_5
            break
          case 6:
            this.displayThisProducts = this.produtosLojaId_6
            break
          case 7:
            this.displayThisProducts = this.produtosLojaId_7
            break
        }
      }
    }
  },

  data: () => ({
    snackbar: false,
    timeout: 2000,
    displayThisProducts: -1,
    produtosLojaId_1: [
      {"nome": "laranja", "preco": 2.00, "emEstoque": 100, "picture": "https://d3ugyf2ht6aenh.cloudfront.net/stores/746/397/products/laranja_ceu1-53852a66aa8037bd7415221636647098-1024-1024.jpg", "qtdProduto":0},
      {"nome": "laranja2", "preco": 2.00, "emEstoque": 100, "picture": "https://villalvafrutas.com.br/wp-content/uploads/2017/08/155.6.546.444994-870x500.jpg", "qtdProduto":0},
      {"nome": "laranja3", "preco": 2.00, "emEstoque": 100, "picture": "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ1p20gTiz2TmlW_90v_qnwYqPnWiahCGKyZNAT_41IAQcnEhoZEXOD36Q7MQJIXXGUghw&usqp=CAU", "qtdProduto":0},
      {"nome": "laranja4", "preco": 2.00, "emEstoque": 100, "picture": "https://static1.conquistesuavida.com.br/articles//3/13/17/3/@/32088-a-laranja-bahia-ou-laranja-de-umbigo-e-article_block_media-2.jpg", "qtdProduto":0},
      {"nome": "laranja5", "preco": 2.00, "emEstoque": 100, "picture": "https://comper.vteximg.com.br/arquivos/ids/182175-1000-1000/207993_laranja_pera.jpg?v=637474404930370000", "qtdProduto":0},
    ],
    produtosLojaId_2: [
      {"nome": "melancia", "preco": 2.00, "emEstoque": 100, "picture": "https://d3ugyf2ht6aenh.cloudfront.net/stores/746/397/products/laranja_ceu1-53852a66aa8037bd7415221636647098-1024-1024.jpg", "qtdProduto":0},
      {"nome": "melancia2", "preco": 2.00, "emEstoque": 100, "picture": "https://villalvafrutas.com.br/wp-content/uploads/2017/08/155.6.546.444994-870x500.jpg", "qtdProduto":0},
      {"nome": "melancia3", "preco": 2.00, "emEstoque": 100, "picture": "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ1p20gTiz2TmlW_90v_qnwYqPnWiahCGKyZNAT_41IAQcnEhoZEXOD36Q7MQJIXXGUghw&usqp=CAU", "qtdProduto":0},
      {"nome": "melancia4", "preco": 2.00, "emEstoque": 100, "picture": "https://static1.conquistesuavida.com.br/articles//3/13/17/3/@/32088-a-laranja-bahia-ou-laranja-de-umbigo-e-article_block_media-2.jpg", "qtdProduto":0},
      {"nome": "melancia5", "preco": 2.00, "emEstoque": 100, "picture": "https://comper.vteximg.com.br/arquivos/ids/182175-1000-1000/207993_laranja_pera.jpg?v=637474404930370000", "qtdProduto":0},
    ],
    produtosLojaId_3: [
      {"nome": "uva", "preco": 2.00, "emEstoque": 100, "picture": "https://d3ugyf2ht6aenh.cloudfront.net/stores/746/397/products/laranja_ceu1-53852a66aa8037bd7415221636647098-1024-1024.jpg", "qtdProduto":0},
      {"nome": "uva2", "preco": 2.00, "emEstoque": 100, "picture": "https://villalvafrutas.com.br/wp-content/uploads/2017/08/155.6.546.444994-870x500.jpg", "qtdProduto":0},
      {"nome": "uva3", "preco": 2.00, "emEstoque": 100, "picture": "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ1p20gTiz2TmlW_90v_qnwYqPnWiahCGKyZNAT_41IAQcnEhoZEXOD36Q7MQJIXXGUghw&usqp=CAU", "qtdProduto":0},
      {"nome": "uva4", "preco": 2.00, "emEstoque": 100, "picture": "https://static1.conquistesuavida.com.br/articles//3/13/17/3/@/32088-a-laranja-bahia-ou-laranja-de-umbigo-e-article_block_media-2.jpg", "qtdProduto":0},
      {"nome": "uva5", "preco": 2.00, "emEstoque": 100, "picture": "https://comper.vteximg.com.br/arquivos/ids/182175-1000-1000/207993_laranja_pera.jpg?v=637474404930370000", "qtdProduto":0},
    ],
    produtosLojaId_4: [
      {"nome": "abacate", "preco": 2.00, "emEstoque": 100, "picture": "https://d3ugyf2ht6aenh.cloudfront.net/stores/746/397/products/laranja_ceu1-53852a66aa8037bd7415221636647098-1024-1024.jpg", "qtdProduto":0},
      {"nome": "abacate2", "preco": 2.00, "emEstoque": 100, "picture": "https://villalvafrutas.com.br/wp-content/uploads/2017/08/155.6.546.444994-870x500.jpg", "qtdProduto":0},
      {"nome": "abacate3", "preco": 2.00, "emEstoque": 100, "picture": "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ1p20gTiz2TmlW_90v_qnwYqPnWiahCGKyZNAT_41IAQcnEhoZEXOD36Q7MQJIXXGUghw&usqp=CAU", "qtdProduto":0},
      {"nome": "abacate4", "preco": 2.00, "emEstoque": 100, "picture": "https://static1.conquistesuavida.com.br/articles//3/13/17/3/@/32088-a-laranja-bahia-ou-laranja-de-umbigo-e-article_block_media-2.jpg", "qtdProduto":0},
      {"nome": "abacate5", "preco": 2.00, "emEstoque": 100, "picture": "https://comper.vteximg.com.br/arquivos/ids/182175-1000-1000/207993_laranja_pera.jpg?v=637474404930370000", "qtdProduto":0},
    ],
    produtosLojaId_5: [
      {"nome": "melao", "preco": 2.00, "emEstoque": 100, "picture": "https://d3ugyf2ht6aenh.cloudfront.net/stores/746/397/products/laranja_ceu1-53852a66aa8037bd7415221636647098-1024-1024.jpg", "qtdProduto":0},
      {"nome": "melao2", "preco": 2.00, "emEstoque": 100, "picture": "https://villalvafrutas.com.br/wp-content/uploads/2017/08/155.6.546.444994-870x500.jpg", "qtdProduto":0},
      {"nome": "melao3", "preco": 2.00, "emEstoque": 100, "picture": "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ1p20gTiz2TmlW_90v_qnwYqPnWiahCGKyZNAT_41IAQcnEhoZEXOD36Q7MQJIXXGUghw&usqp=CAU", "qtdProduto":0},
      {"nome": "melao4", "preco": 2.00, "emEstoque": 100, "picture": "https://static1.conquistesuavida.com.br/articles//3/13/17/3/@/32088-a-laranja-bahia-ou-laranja-de-umbigo-e-article_block_media-2.jpg", "qtdProduto":0},
      {"nome": "melao5", "preco": 2.00, "emEstoque": 100, "picture": "https://comper.vteximg.com.br/arquivos/ids/182175-1000-1000/207993_laranja_pera.jpg?v=637474404930370000", "qtdProduto":0},
    ],
    produtosLojaId_6: [
      {"nome": "fruta", "preco": 2.00, "emEstoque": 100, "picture": "https://d3ugyf2ht6aenh.cloudfront.net/stores/746/397/products/laranja_ceu1-53852a66aa8037bd7415221636647098-1024-1024.jpg", "qtdProduto":0},
      {"nome": "fruta2", "preco": 2.00, "emEstoque": 100, "picture": "https://villalvafrutas.com.br/wp-content/uploads/2017/08/155.6.546.444994-870x500.jpg", "qtdProduto":0},
      {"nome": "fruta3", "preco": 2.00, "emEstoque": 100, "picture": "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ1p20gTiz2TmlW_90v_qnwYqPnWiahCGKyZNAT_41IAQcnEhoZEXOD36Q7MQJIXXGUghw&usqp=CAU", "qtdProduto":0},
      {"nome": "fruta4", "preco": 2.00, "emEstoque": 100, "picture": "https://static1.conquistesuavida.com.br/articles//3/13/17/3/@/32088-a-laranja-bahia-ou-laranja-de-umbigo-e-article_block_media-2.jpg", "qtdProduto":0},
      {"nome": "fruta5", "preco": 2.00, "emEstoque": 100, "picture": "https://comper.vteximg.com.br/arquivos/ids/182175-1000-1000/207993_laranja_pera.jpg?v=637474404930370000", "qtdProduto":0},
    ],
    produtosLojaId_7: [
      {"nome": "tomate", "preco": 2.00, "emEstoque": 100, "picture": "https://d3ugyf2ht6aenh.cloudfront.net/stores/746/397/products/laranja_ceu1-53852a66aa8037bd7415221636647098-1024-1024.jpg", "qtdProduto":0},
      {"nome": "tomate2", "preco": 2.00, "emEstoque": 100, "picture": "https://villalvafrutas.com.br/wp-content/uploads/2017/08/155.6.546.444994-870x500.jpg", "qtdProduto":0},
      {"nome": "tomate3", "preco": 2.00, "emEstoque": 100, "picture": "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ1p20gTiz2TmlW_90v_qnwYqPnWiahCGKyZNAT_41IAQcnEhoZEXOD36Q7MQJIXXGUghw&usqp=CAU", "qtdProduto":0},
      {"nome": "tomate4", "preco": 2.00, "emEstoque": 100, "picture": "https://static1.conquistesuavida.com.br/articles//3/13/17/3/@/32088-a-laranja-bahia-ou-laranja-de-umbigo-e-article_block_media-2.jpg", "qtdProduto":0},
      {"nome": "tomate5", "preco": 2.00, "emEstoque": 100, "picture": "https://comper.vteximg.com.br/arquivos/ids/182175-1000-1000/207993_laranja_pera.jpg?v=637474404930370000", "qtdProduto":0},
    ],
  }),

  methods: {
    addToCart(product, price, quantity){
      let totalPrice = Number(price) * Number(quantity)
      let productName = product

      let productToAdd = {
        "totalPrice": totalPrice,
        "productName": productName,
        "quantity": Number(quantity)
      }
      this.$emit('clicked', productToAdd)
    }
  }
}
</script>

<style scoped>

</style>