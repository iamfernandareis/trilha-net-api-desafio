# DIO - Trilha .NET - API e Entity Framework
www.dio.me

## Desafio de projeto
Para este desafio, você precisará usar seus conhecimentos adquiridos no módulo de API e Entity Framework, da trilha .NET da DIO.

## Configuração do SQL Server

Para rodar este projeto corretamente, é necessário ter uma instância do SQL Server em execução e configurar o acesso conforme a string de conexão presente no arquivo `appsettings.Development.json`:

```json
"ConnectionStrings": {
  "ConexaoPadrao": "Server=localhost;Database=Organizador;User Id=sa;Password=SuaSenhaForte;TrustServerCertificate=True"
}
```

**Passos para configurar:**

1. Instale o SQL Server (pode ser o SQL Server Express, Developer ou via Docker).
2. Crie um usuário `sa` com a senha definida em `SuaSenhaForte` ou altere a string de conexão para refletir o usuário e senha desejados.
3. Certifique-se de que o SQL Server está aceitando conexões TCP/IP na porta padrão (1433).
4. O banco de dados `Organizador` será criado automaticamente ao rodar as migrations, caso não exista.
5. Para aplicar as migrations e criar as tabelas, execute no terminal do projeto:

   ```sh
   dotnet ef database update
   ```

   (Se necessário, instale a ferramenta com `dotnet tool install --global dotnet-ef`.)

6. Caso altere a string de conexão, lembre-se de atualizar o arquivo `appsettings.Development.json`.

## Contexto
Você precisa construir um sistema gerenciador de tarefas, onde você poderá cadastrar uma lista de tarefas que permitirá organizar melhor a sua rotina.

Essa lista de tarefas precisa ter um CRUD, ou seja, deverá permitir a você obter os registros, criar, salvar e deletar esses registros.

A sua aplicação deverá ser do tipo Web API ou MVC, fique a vontade para implementar a solução que achar mais adequado.

A sua classe principal, a classe de tarefa, deve ser a seguinte:

![Diagrama da classe Tarefa](diagrama.png)

Não se esqueça de gerar a sua migration para atualização no banco de dados.

## Métodos esperados
É esperado que você crie o seus métodos conforme a seguir:


**Swagger**


![Métodos Swagger](swagger.png)


**Endpoints**


| Verbo  | Endpoint                | Parâmetro | Body          |
|--------|-------------------------|-----------|---------------|
| GET    | /Tarefa/{id}            | id        | N/A           |
| PUT    | /Tarefa/{id}            | id        | Schema Tarefa |
| DELETE | /Tarefa/{id}            | id        | N/A           |
| GET    | /Tarefa/ObterTodos      | N/A       | N/A           |
| GET    | /Tarefa/ObterPorTitulo  | titulo    | N/A           |
| GET    | /Tarefa/ObterPorData    | data      | N/A           |
| GET    | /Tarefa/ObterPorStatus  | status    | N/A           |
| POST   | /Tarefa                 | N/A       | Schema Tarefa |

Esse é o schema (model) de Tarefa, utilizado para passar para os métodos que exigirem

```json
{
  "id": 0,
  "titulo": "string",
  "descricao": "string",
  "data": "2022-06-08T01:31:07.056Z",
  "status": "Pendente"
}
```


## Solução
O código está pela metade, e você deverá dar continuidade obedecendo as regras descritas acima, para que no final, tenhamos um programa funcional. Procure pela palavra comentada "TODO" no código, em seguida, implemente conforme as regras acima.