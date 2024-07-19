<script setup>
import { ref } from 'vue'
import ProductList from '@/components/ProductList.vue'

const produtos = ref ([
  {id: 1, nome: 'Produto A' , preco: 'R$110,15'},
  {id: 2, nome: 'Produto B' , preco: 'R$210,55'},
  {id: 3, nome: 'Produto C' , preco: 'R$120,37'},
  {id: 4, nome: 'Produto D' , preco: 'R$340,99'}

])

function excluirProduto(id) {
  const index = produtos.value.findIndex((produto) => produto.id === id)
  produtos.value.splice(index, 1)
}

function excluirTodosOsProdutos() {
  produtos.value = []
}
</script>

<template>
  <h1>Meus produtos</h1>
  <product-list :produtos="produtos" @excluir="excluirProduto" @excluirTudo="excluirTodosOsProdutos"/>
</template>

<style scoped></style>