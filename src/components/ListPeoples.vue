<template>
   <div class="container">
    <h2>Itens existentes:</h2>
    <ul id="item-list">
        <li v-for="aluno in alunos" :key="aluno.id">
            
            <strong>{{ aluno.titulo }} {{ aluno.nome }} </strong>
            idade: {{ aluno.idade }}
            linha de pesquisa: {{ aluno.linha_de_pesquisa }}
            <button name={{aluno.uuid}} class="btn-remove">Excluir</button>

        </li>
    </ul>
    <tr v-for="aluno in itens" :key="item.id">
          <td>{{ item.id }}</td>
          <td>{{ item.nome }}</td>
          <td>{{ item.descricao }}</td>
        </tr>

  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import axios from 'axios'; // Importa a biblioteca axios
export default defineComponent({
  name: 'ListPeoples',
  data() {
    return {
      alunos: [] // Array para armazenar os itens da API
    };
  },
  mounted() {
    this.fetchItens(); // Chama a função para buscar os itens ao montar o componente
  },
  methods: {
    fetchItens() {
      // Função para buscar os itens da API
      // Utiliza o método GET do Vue.js para fazer a requisição
      axios.get('http://127.0.0.1:5000/api/aluno')
        .then(response => {
          this.alunos = response.data; // Armazena os itens no array de dados do Vue.js
          console.log(response.data)
        })
        .catch(error => {
          console.error('Erro ao buscar os itens da API:', error);
        });
    }
  }
});
</script>

<style scoped>
.container{
  padding: 1rem 2rem 1rem 2rem;
}
.title{
    padding:0.4rem;
    margin: 0.4rem 0 0.1rem 1.2rem;
    font-size: 1rem;
}

.sessao-conteudo{
  padding: 1rem;
}
.btn, button {
    border: none;
    background-color: green;
    color:#f2f2f2;
    padding: 0.6rem 0.8rem;
    font-size: 1rem;
    border-radius: 1rem;
    cursor: pointer;
    margin: 0 1rem;
}
.btn-remove{
  background-color: rgb(152, 9, 9);  
}

ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

li {
  padding: 10px;
  margin-bottom: 5px;
  background-color: #f7f7f7;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  border-radius: 4px;
}

li:hover {
  background-color: #e0e0e0;
}

li:last-child {
  margin-bottom: 0;
}

</style>
