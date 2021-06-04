<template>
    <v-container fill-height>
      <v-layout align-center>
        <v-flex>
          <h3 class="display-3">Trabalho de Computação Distribuída</h3>

          <div class="title mb-3">Prof. Roberto Aragy - UFMS - 2021.1 - Turma 2</div>
          <span class="subheading">Gerenciamento de lojas, estoques, produtos, usuários e vendas.</span>
          <v-divider class="my-3"></v-divider>

          <v-timeline
              dense
              clipped
          >
            <v-timeline-item
                fill-dot
                class="black--text mb-12"
                color="purple"
                large
            >
              Estrutura
            </v-timeline-item>

            <div v-for="item in estrutura" :key="item.descricao">
              <v-timeline-item
                  class="mb-4"
                  small
                  color="deep-purple lighten-2"
              >
                <v-chip
                    class="white--text ml-0"
                    color="purple darken-4"
                    label
                    small
                >
                  {{ item.chip }}
                </v-chip>
                {{ item.descricao }}

              </v-timeline-item>
            </div>


          </v-timeline>
          <v-timeline
              dense
              clipped
          >
            <v-timeline-item
                fill-dot
                class="black--text mb-12"
                color="cyan"
                large
            >
              Banco
            </v-timeline-item>

            <div v-for="item in banco" :key="item.descricao">
              <v-timeline-item
                  class="mb-4"
                  small
                  color="cyan lighten-2"
              >
                <v-chip
                    class="white--text ml-0"
                    color="cyan darken-4"
                    label
                    small
                >
                  {{ item.chip }}
                </v-chip>
                {{ item.descricao }}

              </v-timeline-item>
            </div>


          </v-timeline>
          <v-timeline
              dense
              clipped
          >
            <v-timeline-item
                fill-dot
                class="black--text mb-12"
                color="green"
                large
            >
              Regras de Negócio
            </v-timeline-item>

            <div v-for="item in regra_de_negocio" :key="item.descricao">
              <v-timeline-item
                  class="mb-4"
                  small
                  color="green lighten-2"
              >
                <v-chip
                    class="white--text ml-0"
                    color="green darken-4"
                    label
                    small
                >
                  {{ item.chip }}
                </v-chip>
                {{ item.descricao }}

              </v-timeline-item>
            </div>


          </v-timeline>
          <v-divider class="my-3"></v-divider>


        </v-flex>
      </v-layout>
    </v-container>
</template>

<script>
export default {
  name: "Sobre",

  data: () => ({
    estrutura: [
      {"descricao": "Vue.js", "chip":"Frontend"},
      {"descricao": "SpringBoot", "chip":"Backend"},
      {"descricao": "REST API", "chip":"Comunicação"}
    ],
    banco: [
      {"descricao": "Postgres", "chip":"Conexão"},
      {"descricao": "Loja, Estoque, Produto, Cargo, Usuario, venda, Venda_Item", "chip":"Tabelas"},
    ],
    regra_de_negocio: [
      {"descricao": "Somente administradores do sistema podem utilizar CRUD de lojas", "chip": "Lojas"},
      {"descricao": "Somente usuários com cargo de gerente podem utilizar CRUD de estoque nas suas respectivas lojas", "chip": "Estoques"},
      {"descricao": "Somente usuários com cargo de gerente podem utilizar CRUD de produtos em seus respectivos estoques", "chip": "Produtos"},
      {"descricao": "Somente usuários logados com cargo de cliente podem utilizar CRUD de vendas", "chip": "Venda"},
      {"descricao": "Somente produtos em estoque podem ser vendidos", "chip": "Venda"},
    ]
  }),
}
</script>

<style scoped>

</style>