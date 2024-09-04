# O que é uma API REST?

Dividir um sistema em camadas ajuda a organizar o código de maneira que cada parte tenha uma responsabilidade clara.
Isso torna o código mais fácil de entender, manter e expandir. 

### API (Application Programming Interface)
Uma API é como um cardápio em um restaurante. Quando você vai a um restaurante, olha o cardápio e escolhe o que deseja.
Você diz ao garçom o que quer e ele vai até a cozinha para trazer a comida. A API funciona de maneira semelhante. Ela é
uma forma de comunicação entre diferentes partes de um software. É um conjunto de regras que permitem que um aplicativo
peça informações ou faça ações em outro aplicativo.

<br>

### REST (Representational State Transfer)
REST é um estilo de arquitetura para criar APIs. É como um guia de boas práticas para criar APIs que sejam fáceis de usar
e entender. REST usa verbos HTTP (como GET, POST, PUT, DELETE) para definir ações. Cada verbo HTTP representa uma ação
diferente:
- **GET**: Usado para pegar (ou obter) informações
- **POST**: Usado para enviar novas informações
- **PUT**: Usado para atualizar informações existentes
- **DELETE**: Usado para deletar informações

<br>

### Estrutura de uma API REST com Camadas
Agora, vamos falar sobre como uma API REST pode ser estruturada em camadas. Isso ajuda a organizar o código e a separar
diferentes responsabilidades, tornando o sistema mais fácil de entender e manter.

##### As Quatro Principais Camadas

1. **Modelo (Model)**: Onde a estrutura dos dados é definida
2. **Repositório (Repository)**: Onde a lógica de acesso a dados é centralizada
3. **Serviço (Service)**: Onde a lógica de negócios é implementada
4. **Controle (Controller)**: Onde as requisições HTTP são gerenciadas

<br>

### 1. Camada de Modelo (Model)

**Responsabilidade**: Definir a estrutura dos dados e, em projetos mais complexos, lidar com a interação direta com o banco
de dados.

  - **O que ela faz no projeto com banco em memória** ( [flask_calculator](https://github.com/Mentoria-Fino-Plataforma-Impact/flask_calculator) ):
      - Define a classe Calculation, que representa um cálculo
      - Esta classe contém atributos que descrevem um cálculo (por exemplo, operação, operandos, resultado) e métodos auxiliares
      - para converter o objeto para um dicionário ou para outra forma que facilite sua manipulação
      - Em uma aplicação mais complexa com um banco de dados real, essa camada também incluiria lógica para consultas, inserções e
      - atualizações no banco de dados
        
  Pense no modelo como uma ficha em uma receita de bolo que anota qual é a operação e os ingredientes (números) necessários.

<br>

### 2. Camada de Repositório (Repository)

**Responsabilidade**: Centralizar e gerenciar a lógica de acesso aos dados. A camada de repositório atua como um intermediário entre a
camada de serviço e os dados reais. Isso ajuda a desacoplar a lógica de negócios da maneira como os dados são armazenados ou recuperados.

   - **O que ela faz no projeto com banco em memória**:
       - Armazena os cálculos em uma lista em memória
       - Fornece métodos para adicionar, listar, atualizar e deletar cálculos dessa lista
       - Se estivéssemos usando um banco de dados real, essa camada se comunicaria com o banco de dados para executar operações CRUD

     Pense no repositório como o assistente do cozinheiro, que mantém um inventário dos ingredientes e os entrega para o cozinheiro conforme
     necessário.

     <br>

### 3. Camada de Serviço (Service)

**Responsabilidade**: Implementar a lógica de negócios, ou seja, como os dados devem ser processados e manipulados. Esta camada não sabe nada
sobre HTTP ou Flask diretamente; apenas trabalha com objetos e lógica de aplicação.

  - **O que ela faz no projeto com banco em memória**:
      - Contém funções para criar, listar, atualizar e deletar cálculos
      - Executa a lógica das operações matemáticas (adição, subtração, multiplicação, divisão)
      - Valida os dados (por exemplo, evitar divisão por zero)
      - Usa o repositório para armazenar e recuperar cálculos

    Pense no serviço como o cozinheiro que faz a operação matemática e calcula o resultado, pedindo os ingredientes para o assistente
    (repositório) e devolvendo os resultados.

    <br>
    
### 4. Camada de Controle (Controller)

**Responsabilidade**: Gerenciar as requisições HTTP, delegar a lógica para a camada de serviço e retornar as respostas para o cliente.

  - **O que ela faz no projeto com banco em memória**:
      - Define as rotas da aplicação (/calculate, /calculations)
      - Recebe as requisições HTTP, extrai os dados e chama a camada de serviço para executar a lógica de negócio
      - Lida com respostas HTTP, incluindo tratamento de erros e formatação de resposta (por exemplo, retornar JSON)

    Pense no controlador como o garçom que recebe o pedido, passa a informação para o cozinheiro e depois entrega o resultado ao cliente.
