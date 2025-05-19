# Caso de Uso: Ativar Cliente

## 🎯 Objetivo
Permitir que um cliente ativo seja marcado como ativo, habilitando seu uso em novas ordens de serviço.


## 📜 Regras de Negócio
- O cliente deve existir no banco de dados
- O cliente deve estar atualmente **Inativo**


## 🚨 Possíveis Erros
- Cliente não encontrado
- Cliente está Inativo


## 📥 Entrada
- `Id` (guid, obrigatório) - Identificador do cliente


## 📤 Saída
- Confirmação de ativação com sucesso
- Mensagem de erro em caso de falha (ex: cliente não encontrado ou já inativo)