<script setup lang="ts">
import { ref } from "vue";

// Array de produtos de exemplo
const produtos = ref([
  { id: 1, nome: "Tênis de Corrida", descricao: "Confortável e leve", preco: 199.99 },
  { id: 2, nome: "Camiseta Esportiva", descricao: "Material respirável", preco: 59.99 },
  { id: 3, nome: "Mochila de Hidratação", descricao: "Capacidade de 2L", preco: 89.99 },
  // Adicione mais produtos conforme necessário
]);
const columnsTable = [
  { title: "Código", value: "id" },
  { title: "Nome", value: "nome" },
  { title: "Descrição", value: "descricao" },
  { title: "Preço", value: "preco" },
  { title: "Ações", value: "acoes" },
];
</script>

<template>
  <v-container class="bg-surface">
    <v-row align="center">
      <v-spacer></v-spacer>
      <v-col cols="2">
        <v-btn color="blue">Novo produto</v-btn>
      </v-col>
      <v-col cols="1">
        <v-icon color="blue">mdi-filter</v-icon>
      </v-col>
    </v-row>
    <!-- Tabela de Caixas -->
    <v-data-table :headers="columnsTable" :items="produtos">
      <template v-slot:item="{ item }">
        <tr>
          <td class="text-center">#{{ item.id }}</td>
          <td class="text-center">{{ item.nome }}</td>
          <td class="text-center">{{ item.descricao }}</td>
          <td class="text-center">{{ item.preco }}</td>
          <td class="text-center">
            <!-- Botão Editar -->
            <v-btn class="mr-2" color="yellow" icon>
              <v-icon>mdi-pencil</v-icon>
            </v-btn>

            <!-- Botão Excluir -->
            <v-btn class="mr-2" color="red" icon>
              <v-icon>mdi-delete</v-icon>
            </v-btn>
          </td>
        </tr>
      </template>
    </v-data-table>
  </v-container>
</template>
