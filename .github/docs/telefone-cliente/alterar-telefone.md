# Caso de Uso: Alterar Telefone

## 🎯 Objetivo
Substituir um telefone existente de um cliente por um novo, garantindo que todas as regras de negócio e validações sejam respeitadas.


## 📜 Regras de Negócio
- O telefone a ser alterado deve pertencer ao cliente informado
- Aplicam-se as mesmas validações do cadastro:
  - DDD com 2 dígitos válidos
  - Número com 8 ou 9 dígitos
  - Tipo de telefone válido
  - `residencial` e `comercial` não aceitam SMS/WhatsApp
- Como o telefone é um **Value Object**, a operação consiste em remover o telefone antigo e adicionar um novo


## 🚨 Possíveis Erros
- Cliente não encontrado
- Telefone original não encontrado ou não pertence ao cliente
- Novo telefone com dados inválidos
- Violação das regras de negócio


## 📥 Entrada
- `IdCliente` (GUID, obrigatório)
- `IdTelefoneAntigo` (GUID, obrigatório)
- Novo objeto `Telefone`:
  - `DDD` (inteiro, obrigatório, 2 dígitos)
  - `Número` (string, obrigatório, 8 ou 9 dígitos)
  - `Tipo` (string, obrigatório: `celular`, `residencial`, `comercial`)
  - `AceitaSMS` (bool, obrigatório)
  - `AceitaWhatsApp` (bool, obrigatório)


## 📤 Saída
- Telefone antigo removido
- Novo telefone adicionado com sucesso
- Mensagem de erro informando inconsistência ou falha na operação


## 👀 Observações
- Ideal manter um histórico da operação para fins de auditoria (fora do escopo do domínio)
- A substituição deve ser atômica — falha em uma etapa invalida a outra