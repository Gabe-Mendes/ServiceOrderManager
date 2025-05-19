# Caso de Uso: Atualizar Cliente

## 🎯 Objetivo
Permitir a alteração dos dados de um cliente previamente cadastrado, mantendo a integridade e regras de negócio aplicáveis.


## 📜 Regras de Negócio
- O cliente deve existir no banco de dados
- O cliente deve conter no mínimo 3 caracteres
- O nome não deve conter apenas espaços em branco
- O telefone será inserido, caso não seja informado o **id-telefone**
- Caso seja informado o **id-telefone**, o telefone será atualizado
- Telefones devem obedecer às **regras de validação definidas no domínio de Telefone**


## 🚨 Possíveis Erros
- O cliente deve existir no banco de dados
- Nome inválido ou ausente
- Telefone inválido ou ausente
- Dados do(s) telefone(s) não seguem as validações de domínio


## 📥 Entrada
- `Id` (guid, obrigatório) - identificador do cliente a ser alterado
- `Nome` (string, opcional, mínimo 3 caracteres)
- `Telefones` (lista de objetos, opcional, substitui ou atualiza os telefones atuais)
    - Cada telefone deve seguir as regras já definidas em **cadastrar-telefone**


## 📤 Saída
- Objeto `Cliente` atualizado com sucesso
- Mensagem de erro clara em caso de falha de validação