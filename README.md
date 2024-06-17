#  API de Receitas

# Orientações

<details>
  <summary><strong>‼️ Executar projeto</strong></summary><br />

  1. Clone o repositório

  - Use o comando: `git clone git@github.com:Mathluiz23/recipe-api.git`.
  - Entre na pasta do repositório que você acabou de clonar:
    - `cd recipe-api`

  2. Instale as dependências
  
  - Entre na pasta `src/`.
  - Execute o comando: `dotnet restore`.

</details>

<details>
  <summary><strong>🛠 Testes</strong></summary><br />

  ### Executando todos os testes

  Para executar os testes com o .NET, execute o comando dentro do diretório do seu projeto `src/recipes-api` ou de seus testes `src/recipes-api.Test`!

  ```
  dotnet test
  ```

  ### Executando um teste específico

  Para executar um teste específico, basta executar o comando `dotnet test --filter Name~TestMethod1`.

</details>


# O projeto

Este é um aplicativo de Receitas que está totalmente funcional 😉. Onde foi desenvolvido uma **api de receitas** que vai retornar todas as receitas disponíveis, será possível também adicionar, remover e atualizar as receitas.

 
## 1 - Implementado funções ReadAll, ReadOne e testes
`Em src/recipes-api/RecipesController.cs`

<details>
  <summary>Implementeado Action para ler todas as receitas</summary><br />

A action é do tipo `HttpGet` e irá retornar uma `IActionResult` do tipo `Ok` com um array com todas as receitas.
  
</details>

<details>
  <summary>Implementado Action para ler uma receita</summary><br />

A action é do tipo `HttpGet` e recebe um parâmetro `name`;

Irá retornar uma `IActionResult` do tipo `Ok` com o objeto do tipo `Recipe` que corresponde à busca.

Se não for encontrada uma receita com o nome passado por parâmetro, a Action irá retornar uma `IActionResult` do tipo `NotFound`.
  
</details>


## 2 - Implementando função Create e testes

`Em src/recipes-api/RecipesController.cs`

<details>
  <summary>Implementadp Action para criar uma nova receita</summary><br />

A action é do tipo `HttpPost`;

Receber uma `Recipe` pelo corpo da requisição;

Se a receita passada por parâmetro for nula, irá retornar um `IActionResult` do tipo `BadRequest`;

A action irá adicionar a receita criada por parâmetro ao service e retornará um `IActionResult` do tipo `CreatedAtRoute` com a receita;
  
</details>

<details>
  <summary>Testes para a função de Create</summary><br />

Implementado em `src/recipes-api.Test/TestRecipesControllerCreate.cs`
  
Irá verificar se, quando chamada a action, ela adiciona corretamente a Recipe para o service.

</details>

## 3 - Implementado  função Update e testes
`Em src/recipes-api/RecipesController.cs`

<details>
  <summary>Implementado  Action para criar uma nova receita</summary><br />

A action é do tipo `HttpPut`;

Receberá uma string de nome por parâmetro e uma `Recipe` pelo corpo da requisição;

Se a receita passada por parâmetro for nula ou o nome passado por parâmetro for diferente do nome da receita, irá retornar um `IActionResult` do tipo `BadRequest`;

A action irá atualizar a receita no service corretamente e retornará um `IActionResult` do tipo `NoContent` com a receita;
  
</details>

<details>
  <summary>Testes para a função de Update</summary><br />

Implementado em `src/recipes-api.Test/TestRecipesControllerUpdate.cs`
  
Irá verificar se, quando chamada a action, ela altera corretamente a Recipe no service.

</details>




## 4 - Implementado  função Delete e testes
`Em src/recipes-api/RecipesController.cs`

<details>
  <summary>Implementado  Action para deletar uma nova receita</summary><br />

A action é tipo `HttpDelete`;

Receberá uma string de nome por parâmetro;

Se a receita a ser deletada não existir no service, irá retornar um `IActionResult` do tipo `NotFound`;

A action deve deletar a receita no service corretamente e retornará um `IActionResult` do tipo `NoContent` com a receita;
  
</details>

<details>
  <summary>Testes para a função de Delete</summary><br />

Implementando em `src/recipes-api.Test/TestRecipesControllerDelete.cs`
  
Irá verificar se, quando chamada a action, ela deleta corretamente a Recipe no service.

</details>
