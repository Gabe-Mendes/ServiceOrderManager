# Caso de Uso: Encerrar Ordem de Serviço

## 🎯 Objetivo
Permitir o encerramento de uma ordem de serviço, registrando a data de finalização e alterando seu status.


## 📜 Regras de Negócio
- A ordem de serviço deve existir no sistema
- A ordem deve estar ativa (não pode estar encerrada ou inativa)
- O campo `DataEncerramento` deve ser preenchido com a data/hora atual no momento do encerramento
- Após o encerramento:
    - O status da ordem é alterado para Inativa
    - A ordem não poderá mais ser modificada


## 🚨 Possíveis Erros
- Ordem de serviço não encontrada
- Ordem já encerrada ou inativa
- Erro ao salvar alterações no banco


## 📥 Entrada
- `IdOrdemDeServico` (guid, obrigatório)


## 📤 Saída
- Confirmação de encerramento da ordem
- Objeto `OrdemServico` atualizado com `DataEncerramento`, `Status`: `Inativo`


## 👀 Observações
- O encerramento representa a conclusão de um serviço prestado
- Encerramentos automáticos podem ser considerados futuramente para serviços agendados