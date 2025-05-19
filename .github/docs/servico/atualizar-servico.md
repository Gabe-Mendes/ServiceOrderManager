# Caso de Uso: Atualizar Serviço

## 🎯 Objetivo
Permitir a atualização dos dados de um serviço previamente cadastrado.


## 📜 Regras de Negócio
- O serviço informado deve existir
- A descrição não pode ser vazia ou nula
- O tempo de execução deve ser maior que 0
- Um serviço inativo pode ser atualizado normalmente, inclusive reativado


## 🚨 Possíveis Erros
- Serviço não encontrado
- Dados inválidos (ex: tempo de execução menor ou igual a zero)


## 📥 Entrada
- `Id` (guid, obrigatório)
- `Descrição` (string, obrigatório)
- `Tempo de Execução Estimado` (integer, obrigatório, em minutos)
- `Somente Ativos` (boolean, obrigatório)


## 📤 Saída
- Objeto `Serviço` atualizado com sucesso
- Mensagem de erro em caso de falha na validação ou inexistência do serviço


## 👀 Observações
- Não há versionamento dos dados (atualização sobrescreve os dados anteriores)
- Pode ser necessário validar se o novo nome conflita com outro serviço já existente (opcional)