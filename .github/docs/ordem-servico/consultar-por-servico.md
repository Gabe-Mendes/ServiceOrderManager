# Caso de Uso: Consultar Ordem de Serviço por Serviço

## 🎯 Objetivo
Listar todas as ordens de serviço associadas a um cliente específico.


## 📜 Regras de Negócio
- O Serviço deve existir no sistema
- Retornar ordens **ativas** e **inativas**, ordenadas por DataAbertura (decrescente)
- Caso o serviço esteja inativo, a consulta ainda é permitida
- Caso o serviço não possua ordens, retornar lista vazia
- Se a `DataInicio` for preenchida, as Ordens de Serviço listadas deverão ter `DataAbertura` **após** desta data
- Se a `DataFim` for preenchida, as Ordens de Serviço listadas deverão ter `DataAbertura` **depois** desta data
- A `DataInicio` deve ser anterior a `DataFim`, caso ambos sejam preenchidos


## 🚨 Possíveis Erros
- Serviço não encontrado ou inativo


## 📥 Entrada
- `IdServico` (guid, obrigatório)
- `DataInicio` (datetime, opcional) - início do período do filtro
- `DataFim` (datetime, opcional) - final do período do filtro



## 📤 Saída
- Lista de objetos `OrdemServico`, contendo:
    - `Id`
    - `IdCliente`
    - `IdServico`
    - `DataAbertura`
    - `DataEncerramento` (caso exista)
    - `Status` (Ativo / Inativo)
    - `DescricaoServico` (para exibição)


## 👀 Observações
- Ideal para exibição de histórico de serviços por serviço
- Pode ser expandido para aceitar filtros adicionais no futuro (período, status etc.)