<template>
  <v-row>
    <v-card
        v-for="loja in lojas" :key="loja.nome"
        class="mx-auto my-12"
        max-width="374"
    >
      <v-img
          height="350"
          v-bind:src="loja.picture"
      ></v-img>

      <v-card-title>{{ loja.nome }}</v-card-title>

      <v-card-text>
        <v-row
            align="center"
            class="mx-0"
        >
        </v-row>
      </v-card-text>

      <v-divider class="mx-4"></v-divider>


      <v-card-actions>
        <v-btn
            color="deep-purple lighten-2"
            outlined
            @click="renderLojaSelecionada(loja.id)"
        >
          Visitar
        </v-btn>
      </v-card-actions>
    </v-card>
  </v-row>
</template>

<script>
export default {
  name: "Lojas",

  data: () => ({
    lojas: [
      {"id": 1, "nome": "loja1", "picture": "https://www.galeriadaarquitetura.com.br/Img/projeto/SF1/2043/la-fruteria-boutique-de-frutas483.jpg"},
      {"id": 2, "nome": "loja2", "picture": "https://www.galeriadaarquitetura.com.br/Img/projeto/SF1/2043/la-fruteria-boutique-de-frutas494.jpg"},
      {"id": 3, "nome": "loja3", "picture": "https://www.galeriadaarquitetura.com.br/Img/projeto/SF1/2043/la-fruteria-boutique-de-frutas495.jpg"},
      {"id": 4, "nome": "loja4", "picture": "https://coisasdojapao.com/wp-content/uploads/2019/09/sembikiya-emporio-frutas-japao_opt.jpg"},
      {"id": 5, "nome": "loja5", "picture": "https://www.coisasdojapao.com/wp-content/uploads/2019/09/sembikiya_opt.jpg"},
      {"id": 6, "nome": "loja6", "picture": "https://d28dpoj42hxr8c.cloudfront.net/files/user/201908081905_1.jpg?v=1565258741"},
      {"id": 7, "nome": "loja7", "picture": "https://www.galeriadaarquitetura.com.br/Img/projeto/SF1/2043/la-fruteria-boutique-de-frutas4725.jpg"}
    ],
  }),

  methods: {
    renderLojaSelecionada(lojaId){
      this.$emit('clicked', lojaId)
    }
  }
}
</script>

<style scoped>

</style>