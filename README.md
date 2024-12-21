# TDD - Test Driven Development

Este projeto tem como objetivo demonstrar a aplicação prática do **Desenvolvimento Orientado por Testes** (TDD - Test Driven Development) em Java. Ele segue a abordagem de escrever testes antes da implementação do código, garantindo que cada funcionalidade atenda aos requisitos esperados desde o início.

## Funcionalidades

- Implementação de TDD com exemplos práticos.
- Testes unitários detalhados para todas as funcionalidades do projeto.
- Demonstração de como criar endpoints RESTful com Java.
- Cobertura de cenários de sucesso e falha.



## Tecnologias Utilizadas

- **Java**: Linguagem principal do projeto.
- **Spring Boot**: Framework para criação de APIs RESTful.
- **JUnit 5**: Framework para a criação e execução de testes unitários.
- **Maven**: Gerenciador de dependências e automação do projeto.



## Estrutura do Projeto

```
TDD-test-driven-development/
├── src/
│   ├── main/
│   │   ├── java/com/exemplo/tdd/     # Código principal
│   │   │   ├── controller/           # Controladores (endpoints)
│   │   │   ├── service/              # Lógica de negócios
│   │   │   └── model/                # Modelos de dados
│   │   └── resources/                # Configurações
│   └── test/
│       └── java/com/exemplo/tdd/     # Testes unitários
├── pom.xml                           # Configuração do Maven
├── README.md                         # Documentação do projeto
└── .gitignore                        # Configurações para ignorar arquivos
```



## Implementação do TDD

O fluxo de TDD neste projeto segue os três passos clássicos:

1. **Escrever um teste que falha**:
   - Um teste inicial é escrito para validar uma funcionalidade que ainda não existe.
   - Exemplo: validar que a soma de dois números retorna o valor correto.

2. **Fazer o teste passar**:
   - A implementação mínima é feita para que o teste passe.
   - Exemplo: criar um método `soma()` na classe de serviço para retornar o valor correto.

3. **Refatorar o código**:
   - Melhorar a implementação sem alterar o comportamento testado, mantendo os testes verdes.
   - Exemplo: otimizar a lógica ou renomear variáveis para maior clareza.



## Endpoints Implementados

### 1. **Soma de Números**
- **Método:** `POST`
- **URL:** `/api/v1/soma`
- **Descrição:** Recebe dois números e retorna o resultado da soma.
- **Exemplo de Payload:**
  ```json
  {
    "numero1": 5,
    "numero2": 10
  }
  ```
- **Resposta (200):**
  ```json
  {
    "resultado": 15
  }
  ```



### 2. **Subtração de Números**
- **Método:** `POST`
- **URL:** `/api/v1/subtracao`
- **Descrição:** Recebe dois números e retorna o resultado da subtração.
- **Exemplo de Payload:**
  ```json
  {
    "numero1": 15,
    "numero2": 10
  }
  ```
- **Resposta (200):**
  ```json
  {
    "resultado": 5
  }
  ```



## Testes Implementados

### Testes Unitários
- **Classe:** `SomaServiceTest`
  - Testa o método `soma()`, verificando se ele retorna o valor correto.
  - Cenários testados:
    - Soma de dois números positivos.
    - Soma com um número negativo.
    - Soma com zero.

- **Classe:** `SubtracaoServiceTest`
  - Testa o método `subtracao()`, garantindo que o valor retornado esteja correto.
  - Cenários testados:
    - Subtração de dois números positivos.
    - Subtração resultando em valor negativo.
    - Subtração com zero.

### Testes de Integração
- **Classe:** `SomaControllerTest`
  - Testa o endpoint `/api/v1/soma`, verificando:
    - Resposta com sucesso (200).
    - Resposta de erro (400) ao enviar payload inválido.

- **Classe:** `SubtracaoControllerTest`
  - Testa o endpoint `/api/v1/subtracao`, verificando:
    - Resposta com sucesso (200).
    - Resposta de erro (400) ao enviar payload inválido.

### Cobertura de Código
Os testes são escritos para cobrir:
- Casos de sucesso e falha.
- Validação de entradas inválidas (ex.: números nulos ou strings em vez de números).



## Como Executar os Testes

1. **Rodar todos os testes**:
   ```bash
   mvn test
   ```

2. **Gerar relatório de cobertura de testes** (opcional, utilizando o plugin `jacoco`):
   ```bash
   mvn test jacoco:report
   ```
   O relatório será gerado no diretório `target/site/jacoco/index.html`.!
