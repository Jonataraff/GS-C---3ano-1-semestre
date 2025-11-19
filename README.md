👤 Integrantes
**Jonata Rafael - RM552939
**Diogo Julio - RM553837


# 🎓 SkillUp API  
API desenvolvida como parte da avaliação da disciplina de Engenharia de Software / FIAP.  
O projeto simula uma plataforma de Upskilling e Reskilling, permitindo o cadastro de **Trilhas de Aprendizagem** e **Usuários**.

---

## 📚 **Sumário**
- [Descrição do Projeto](#descrição-do-projeto)
- [Arquitetura](#arquitetura)
- [Tecnologias Utilizadas](#tecnologias-utilizadas)
- [Estrutura do Projeto](#estrutura-do-projeto)
- [Configuração do Ambiente](#configuração-do-ambiente)
- [Rodando o Projeto](#rodando-o-projeto)
- [Banco de Dados e Migrations](#banco-de-dados-e-migrations)
- [Endpoints da API](#endpoints-da-api)
- [Tratamento de Erros](#tratamento-de-erros)
- [Diagrama de Arquitetura](#diagrama-de-arquitetura)
- [Autor](#autor)

---

## 📝 **Descrição do Projeto**

A **SkillUp API** oferece operações CRUD para:

- **Usuários**
- **Trilhas de Aprendizagem**

Com banco de dados **SQL Server LocalDB**, uso de **Entity Framework Core**, **Migrations**, **Seed inicial**, **tratamento global de erros** e documentação com **Swagger**.

A API segue uma arquitetura limpa baseada em camadas:

- API (Controllers)
- Application (Services)
- Domain (Entities)
- Infrastructure (EF Core, Migrations, Repositories)

---

## 🏛️ **Arquitetura**

A solução implementa uma arquitetura simples e organizada:

Client (Swagger)
↓
API Layer (Controllers)
↓
Application Layer (Services)
↓
Domain Layer (Entities)
↓
Infrastructure Layer (EF Core / Migrations)
↓
SQL Server LocalDB

arduino
Copiar código

O arquivo do diagrama pode ser encontrado em:
/docs/skillup_architecture.drawio

markdown
Copiar código

---

## 🛠 **Tecnologias Utilizadas**

- **.NET 8 / ASP.NET Core 8**
- **C#**
- **Entity Framework Core**
- **SQL Server LocalDB**
- **Swagger / OpenAPI**
- **Migrations / Code-First**
- **Dependency Injection**
- **Tratamento global de exceções**
- **RESTful API**

---

## 📁 **Estrutura do Projeto**

SkillUp.Api
┣ Controllers
┃ ┣ UsuariosController.cs
┃ ┗ TrilhasController.cs
┣ Domain
┃ ┣ Usuario.cs
┃ ┗ Trilha.cs
┣ Services
┃ ┣ UsuarioService.cs
┃ ┗ TrilhaService.cs
┣ Data
┃ ┣ ApplicationDbContext.cs
┃ ┗ Migrations/
┣ Exceptions
┃ ┣ NotFoundException.cs
┃ ┗ ExceptionMiddleware.cs
┣ Program.cs
┗ appsettings.json

yaml
Copiar código

---

## ⚙️ **Configuração do Ambiente**

### Requisitos:
- Windows 10 ou superior
- Visual Studio 2022
- .NET 8 SDK
- SQL Server LocalDB (vem instalado com o Visual Studio)
- Pacote NuGet:
  - Microsoft.EntityFrameworkCore
  - Microsoft.EntityFrameworkCore.SqlServer
  - Microsoft.EntityFrameworkCore.Tools
  - Swashbuckle.AspNetCore

---

## ▶️ **Rodando o Projeto**

### 1) Restaurar dependências
No Visual Studio, abrir o **Package Manager Console**:

Update-Package

shell
Copiar código

### 2) Aplicar migrations

Update-Database

markdown
Copiar código

### 3) Executar a API
Pressione **F5** ou:

dotnet run

shell
Copiar código

### 4) Acessar no navegador:

https://localhost:7039/swagger

yaml
Copiar código

---

## 🗄️ **Banco de Dados e Migrations**

O projeto usa **Code First + Migrations**.

### Criar uma nova migration:
Add-Migration NomeDaMigration

shell
Copiar código

### Aplicar no banco:
Update-Database

bash
Copiar código

### Seed inicial incluso:
- 3 Trilhas serão inseridas automaticamente:
  - Desenvolvimento Web
  - Inteligência Artificial
  - Soft Skills

---

## 📡 **Endpoints da API**

### **Usuários**
| Método | Rota | Descrição |
|-------|------|-----------|
| GET | /api/v1/usuarios | Lista todos |
| GET | /api/v1/usuarios/{id} | Busca usuário por ID |
| POST | /api/v1/usuarios | Cria usuário |
| PUT | /api/v1/usuarios/{id} | Atualiza |
| DELETE | /api/v1/usuarios/{id} | Remove |

### **Trilhas**
| Método | Rota | Descrição |
|-------|------|-----------|
| GET | /api/v1/trilhas | Lista todas |
| GET | /api/v1/trilhas/{id} | Busca por ID |
| POST | /api/v1/trilhas | Cria trilha |
| PUT | /api/v1/trilhas/{id} | Atualiza |
| DELETE | /api/v1/trilhas/{id} | Remove |

---

## 🚨 **Tratamento de Erros**

A API implementa **middleware global de exceções**, retornando JSON padronizado como:

```json
{
  "status": 404,
  "error": "ResourceNotFound",
  "message": "Trilha não encontrada.",
  "timestamp": "2025-11-19T10:49:21Z"
}
Erros tratados:

400 – Dados inválidos

404 – Recurso não encontrado

500 – Erro interno inesperado

🖼️ Diagrama de Arquitetura
O arquivo pode ser encontrado em:

bash
Copiar código
/docs/skillup_architecture.drawio
Ou diretamente no repositório:

skillup_architecture.drawio

👤 Autor
Jonata Rafael - RM552939
Diogo Julio - RM553837

FIAP – Global Solution 2025
