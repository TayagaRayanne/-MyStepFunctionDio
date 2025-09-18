# AWS Step Functions - Exemplo de Fluxo de Trabalho Condicional

Este projeto é uma atividade de aula do bootcamp CodeGirl AWS da Dio para demonstrar a criação e o uso de uma máquina de estado simples no AWS Step Functions.

### Descrição do Fluxo de Trabalho

O fluxo de trabalho foi projetado para simular uma lógica de decisão simples, onde a execução segue um caminho de "sucesso" ou "falha" com base em uma entrada de dados. Ele é composto por três estados principais:

1.  **`Pass` State Inicial**: Um estado simples que passa a entrada (`{"data": true}` ou `{"data": false}`) para a próxima etapa.
2.  **`Choice` State**: O coração da lógica. Este estado verifica o valor da variável `$.data` e decide qual caminho seguir.
    * Se `$.data` for `true`, o fluxo avança para o estado `Success`.
    * Se `$.data` for `false`, o fluxo avança para o estado `Failure`.
    * Um caminho `Default` garante que qualquer entrada inesperada também resulte em `Failure`.
3.  **`Success` e `Failure` States**: Estados finais que simplesmente indicam o resultado da execução. Eles servem para documentar o caminho que o fluxo de trabalho tomou.

### Arquivos do Repositório

* **`README.md`**: Este arquivo de documentação.
* **`state_machine_definition.json`**: O código-fonte em **Amazon States Language (ASL)** que define a estrutura da máquina de estado. Este código pode ser copiado e colado diretamente no console da AWS para recriar o fluxo de trabalho.

### Como Testar

Você pode iniciar uma execução da máquina de estado no console da AWS e fornecer uma das seguintes entradas no formato JSON:

**Para um resultado de sucesso:**
```json
{
  "data": true
}

**Para um resultado de falha:**
```json
{
  "data": false
}

Criado por: Tayaga Rayanne
