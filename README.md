# ServiceOrderManager

Gerenciador de Ordens de Serviço desenvolvido com foco em Clean Architecture, Domain-Driven Design (DDD), e boas práticas de separação de responsabilidades.

---

## 🚀 Tecnologias Utilizadas

- [.NET 8](https://learn.microsoft.com/en-us/dotnet/)
- Clean Architecture
- Domain-Driven Design (DDD)
- ASP.NET Web API
- C#
- GitHub Actions (CI/CD)
- Mermaid.js (diagramas)
- Visual Studio Code

---

## 🧱 Estrutura do Projeto

```text
ServiceOrderManager.sln
├── ServiceOrderManager.Domain         → Entidades de negócio e interfaces
├── ServiceOrderManager.Application    → Casos de uso, DTOs, interfaces de serviços
├── ServiceOrderManager.Infrastructure → Implementações técnicas (EF, repos, etc.)
└── ServiceOrderManager.Api            → Ponto de entrada (Web API)
```

```mermaid
  graph TD;
      A[API - Presentation Layer]-->B[Application Layer];
      B-->C[Domain Layer];
      B-->D[Infrastructure Layer];
      D-->C;
      classDef layer fill:#94f,stroke:#330,stroke-width:2px; class A,B,C,D layer;
```

# Clone o repositório
git clone https://github.com/Gabe-Mendes/ServiceOrderManager.git

# Acesse o diretório gerado
cd ServiceOrderManager

# Restaure os pacotes
dotnet restore

# Rode a aplicação
dotnet run --project ServiceOrderManager.Api
