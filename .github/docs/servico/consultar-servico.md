# Caso de Uso: Consultar Serviço

## 🎯 Objetivo
Permitir a consulta de serviços cadastrados, com filtros opcionais por nome e status (ativo/inativo).


## 📜 Regras de Negócio
- A busca por descrição deve ignorar maiúsculas/minúsculas (case-insensitive)
- Quando o filtro "Somente Ativos" estiver habilitado, serviços inativos devem ser ignorados
- Se nenhum filtro for informado, todos os serviços ativos serão listados por padrão


## 🚨 Possíveis Erros
- Nenhum (busca tolerante; uma consulta sem resultado não é considerada erro)


## 📥 Entrada
- `Descrição` (string) - busca aproximada (like)
- `Somente Ativos` (boolean, default: true)


## 📤 Saída
- Lista de objetos `Serviço` contendo:
    - `Id`
    - `Descrição`
    - `Tempo de Execução Estimado (min)`
    - `Ativo`


## 👀 Observações
- Ideal para exibição em combos ou filtros nas Ordens de Serviço
- Consultas podem ser paginadas no futuro, se necessário