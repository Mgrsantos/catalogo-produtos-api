# Catálogo de Produtos API

API RESTful desenvolvida com ASP.NET Core e Entity Framework Core para gerenciamento de produtos.

## Tecnologias

- .NET 10
- ASP.NET Core Web API
- Entity Framework Core
- SQLite

## Estrutura do Projeto

CatalogoProdutos.API/
├── Controllers/    # Endpoints HTTP
├── Data/           # DbContext e configuração do banco
├── Migrations/     # Histórico de migrações do banco
├── Models/         # Classes de domínio
├── Services/       # Regras de negócio
└── Program.cs      # Configuração da aplicação

## Endpoints

| Método | Rota | Descrição |
|--------|------|-----------|
| GET | /api/produtos | Lista todos os produtos ativos |
| GET | /api/produtos/{id} | Busca produto por ID |
| POST | /api/produtos | Cadastra novo produto |
| PUT | /api/produtos/{id} | Atualiza produto existente |
| DELETE | /api/produtos/{id} | Remove produto (soft delete) |

## Como executar

Pré-requisitos: .NET 10 SDK instalado

git clone https://github.com/Mgrsantos/catalogo-produtos-api.git
cd catalogo-produtos-api
dotnet restore
dotnet ef database update
dotnet run

A API estará disponível em http://localhost:5074

## Exemplo de requisição

POST /api/produtos
{
  "nome": "Monitor LG",
  "descricao": "Monitor 27 polegadas 4K",
  "preco": 1800.00,
  "quantidadeEstoque": 15
}

## Conceitos aplicados

- Arquitetura em camadas (Controller → Service → Repository)
- Injeção de dependência
- Interface e implementação (IProdutoService)
- LINQ para consultas
- Soft delete
- Migrations com EF Core
