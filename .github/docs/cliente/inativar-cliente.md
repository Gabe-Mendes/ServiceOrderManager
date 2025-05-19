# Caso de Uso: Inativar Cliente

## 🎯 Objetivo
Permitir que um cliente ativo seja marcado como inativo, desabilitando seu uso em novas ordens de serviço.


## 📜 Regras de Negócio
- O cliente deve existir no banco de dados
- O cliente deve estar atualmente **Ativo**
- Clientes inativos não podem ser utilizados em novas ordens de serviço
- A inativação não exclui o cliente nem seus dados relacionados (telefones, ordens anteriores etc.)
- O cliente não poderá ser Inativado caso exista uma Ordem de Serviço ativa atrelado ao Cliente

## 🚨 Possíveis Erros
- Cliente não encontrado
- Cliente está Inativo


## 📥 Entrada
- `Id` (guid, obrigatório) - Identificador do cliente


## 📤 Saída
- Confirmação de inativação com sucesso
- Mensagem de erro em caso de falha (ex: cliente não encontrado ou já inativo)


## 👀 Observações
- A inativação é uma **alteração de estado**, e não implica em perda de dados históricos