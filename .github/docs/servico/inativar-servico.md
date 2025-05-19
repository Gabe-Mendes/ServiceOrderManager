# Caso de Uso: Inativar Serviço

## 🎯 Objetivo
Inativar um serviço cadastrado, tornando-o indisponível para novas ordens de serviço.


## 📜 Regras de Negócio
- O serviço informado deve existir
- O serviço deve estar ativo no momento da solicitação
- Um serviço inativo não pode ser inativado novamente (ação idempotente com resposta adequada)


## 🚨 Possíveis Erros
- Serviço não encontrado
- Serviço já está inativo


## 📥 Entrada
- `Id` (guid, obrigatório)


## 📤 Saída
- Confirmação de inativação com sucesso
- Mensagem de erro em caso de falha na validação ou inexistência do serviço


## 👀 Observações
- Serviços inativos ainda podem ser visualizados (ex: em histórico de ordens)
- Serviços inativados podem ser reativados através do caso de uso de atualização, se necessário