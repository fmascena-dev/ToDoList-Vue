# 📜 Lista de Tarefas - Vue.js

*Este é um projeto simples de uma Lista de Tarefas desenvolvido com* **Vue.js.** *Ele permite que os usuários adicionem e removam tarefas, com uma interface minimalista e animada.*

### 📋 Funcionalidades:

- *Adicionar tarefas à lista;*
- *Remover tarefas da lista;*
- *Mensagem de conclusão quando todas as tarefas forem removidas;*
- *Animação de fundo dinâmica.*

### 🛠️ Tecnologias Utilizadas:

- **Vue.js 3:** *Framework JavaScript para construção de interfaces dinâmicas;*
- **HTML5 e SCSS:** *Estrutura e estilização do projeto.*

### 🚀 Como Executar:

- Pré-requisitos
    - Certifique-se de ter instalado:

        - Node.js
        - Gerenciador de pacotes (npm ou yarn)

#### Clonar o repositório:

```
git clone https://github.com/fmascena-dev/ToDoList-Vue.git  
cd ToDoList-Vue
``` 

#### Instalar dependências:

```
npm install
```

#### Executar o projeto:

```
npm run dev
```

#### Acessar no navegador:

- O projeto estará disponível em:

```
http://localhost:3000
```

### 📂 Estrutura do Projeto:

- **script setup:** *Contém o código Vue responsável pelo gerenciamento da lista de tarefas (adicionar/remover);*

- **template:** *Define a interface visual com mensagens dinâmicas e listas geradas automaticamente;*

- **style scoped lang="scss":** *Estilização moderna e responsiva, com animações de gradiente no fundo.*


### 🖼️ Interface:

1. *Tela Inicial com tarefas padrão;*
2. *Mensagem de conclusão.*

### 🔧 Detalhes do Código:

- **Script:**
    - **tarefas:** *Array reativo com as tarefas atuais;*
    - **novaTarefa:** *String que armazena a entrada do usuário para nova tarefa;*
- **Funções:**
    - **adicionarTarefa():** *Adiciona uma nova tarefa ao array tarefas (se não estiver vazia);*
    - **removerTarefa(index):** *Remove uma tarefa específica com base no índice;*
- **Estilo:**
    - **Gradiente Animado:**
        - *O fundo utiliza uma animação com @keyframes, criando um efeito dinâmico e agradável.*

- **Responsividade:**
    - *O layout foi ajustado para funcionar bem em telas pequenas e grandes.*

### ✨ Contribuições:

- *Contribuições são bem-vindas! Sinta-se à vontade para abrir issues ou enviar pull requests.*