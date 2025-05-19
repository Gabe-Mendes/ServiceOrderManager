# Caso de Uso: Excluir Telefone de um Cliente

## 🎯 Objetivo
- Permitir a exclusão de um número de telefone associado a um cliente


## 📜 Regras de Negócio
- O telefone deve estar associado ao cliente informado
- Não é possível excluir um telefone inexistente
- A exclusão consiste em remover o telefone da lista do cliente, já que é um Value Object


## 🚨 Possíveis Erros
- Cliente não encontrado
- Telefone não encontrado
- Telefone não pertence ao cliente informado


## 📥 Entrada
- `IdCliente` (GUID, obrigatório)
- `IdTelefone` (GUID, obrigatório)


## 📤 Saída
- Confirmação de exclusão com status de sucesso
- Mensagem de erro informando o motivo da falha, se ocorrer


## 👀 Observações
- Como o telefone é um **Value Object**, a exclusão deve ser feita diretamente na coleção do agregado Cliente
- Essa operação pode implicar em validações no momento do commit de agregados (por exemplo, através de um ClienteValidator)