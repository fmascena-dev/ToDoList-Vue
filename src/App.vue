<script setup>
import { ref } from 'vue';

// Lista inicial de tarefas
const tarefas = ref(['Estudar React.js', 'Praticar exercícios de programação']);
// Armazena a nova tarefa do input
const novaTarefa = ref('');

// Função para adicionar uma tarefa
function adicionarTarefa() {
  if (novaTarefa.value.trim() !== '') { // Verifica se o input não está vazio,
// !==: Verifica se os valores e os tipos são diferentes.
    tarefas.value.push(novaTarefa.value.trim()); // Adiciona a nova tarefa na lista
    novaTarefa.value = ''; // Limpa o campo de texto
  }
}

// Função para remover uma tarefa pelo índice
function removerTarefa(index) {
  tarefas.value.splice(index, 1); // Remove 1 item da lista na posição 'index'
}
</script>

<template>
  <main class="app">
    <h1>📜 Lista de tarefas</h1>
    <!-- Mensagem quando não há tarefas -->
    <div v-if="tarefas.length === 0">
      <p>🎉 Parabéns! Você completou todas as tarefas!</p>
    </div>
    <!-- Lista de tarefas usando v-for -->
    <ul v-else>
      <!-- O v-for serve para fazer um loop e criar vários elementos com base em uma lista. -->
      <li v-for="(tarefa, index) in tarefas" :key="index">
        {{ tarefa }}
        <!-- Para cada tarefa (item) da lista tarefas, crie um <li> e me dê também o índice (posição) dessa tarefa. -->
        <!-- tarefa: Representa o item atual da lista, ou seja, cada valor dentro do array tarefas -->
        <!--  index: Representa a posição do item na lista (começa no 0).-->
        <!-- O atributo :key é usado pelo Vue para identificar cada item da lista de forma única. -->
        <button @click="removerTarefa(index)">❎ Remover</button>
      </li>
    </ul>
    <!-- Adicionar nova tarefa -->
    <div class="adicionar-tarefa">
      <!-- v-model sincroniza um valor de uma variavel -->
      <input
        v-model="novaTarefa"
        type="text"
        placeholder="Digite uma nova tarefa"
      />
      <button @click="adicionarTarefa">✅ Adicionar</button>
    </div>
  </main>
</template>

<style scoped lang="scss">
.app {
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  gap: 1rem;
  font-family: Arial, sans-serif;
  text-align: center;
  background: linear-gradient(-45deg, rgba(0, 0, 0, 1), rgba(22, 22, 22, 1), rgba(0, 153, 184, 1));
  background-size: 400% 400%;
  animation: gradientShift 15s ease infinite;

  @keyframes gradientShift {
    0% {
      background-position: 0% 50%;
    }

    50% {
      background-position: 100% 50%;
    }

    100% {
      background-position: 0% 50%;
    }
  }

  h1 {
    font-size: 2.5rem;
    color: #fff;
  }
}

ul {
  list-style: none;
  padding: 0;
  width: 30%;
}

li {
  width: 100%;
  margin: 10px 0;
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: #ffffff;
  color: #000;
  padding: 10px;
  border-radius: 8px;
}

button {
  background: #ff0000;
  color: white;
  border: none;
  border-radius: 5px;
  padding: 5px 10px;
  cursor: pointer;
  font-size: 1rem;
}

button:hover {
  background: transparent;
  box-shadow: 1px 1px 10px 5px rgba(255, 0, 0, 1);
  color: #000;
  transform: scale(1.1);
}

.adicionar-tarefa {
  width: 30%;
  display: flex;
  justify-content: space-between;
}

.adicionar-tarefa input {
  width: 60%;
  padding: 0.6rem;
  border: 1px solid #ccc;
  border-radius: 8px;

  &::placeholder {
    font-size: 16px;
    color: #000000;
  }
}

.adicionar-tarefa button {
  background: transparent;
  color: white;
  border: 1px solid #fff;
  border-radius: 8px;
  padding: 8px 15px;
  margin-left: 10px;
  cursor: pointer;
  font-size: 1rem;
}

.adicionar-tarefa button:hover {
  box-shadow: 1px 1px 10px 5px rgba(0, 153, 184, 1);
  border: 1px solid rgba(0, 153, 184, 1);
  transform: scale(1.1);
}
</style>
