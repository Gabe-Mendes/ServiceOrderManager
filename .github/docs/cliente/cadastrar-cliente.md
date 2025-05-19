# Caso de Uso: Cadastrar Cliente

## 🎯 Objetivo
Cadastrar um novo cliente no sistema com dados básicos e ao menos um telefone válido.


## 📜 Regras de Negócio
- O nome do cliente deve conter no mínimo 3 caracteres
- O nome não deve conter apenas espaços em branco
- Deve haver pelo menos um telefone válido vinculado no momento do cadastro
- Telefones devem obedecer às **regras de validação definidas no domínio de Telefone**
- O campo Ativo deve ser inicializado como true no cadastro


## 🚨 Possíveis Erros
- Nome inválido ou ausente
- Lista de telefones vazia ou com todos inválidos
- Dados do(s) telefone(s) não seguem as validações de domínio


## 📥 Entrada
- `Nome` (string, obrigatório)
- `Data de Inclusão` (datetime, gerado automaticamente pelo sistema)
- `Telefones` (lista de objetos `Telefone`, obrigatório ao menos um)


## 📤 Saída
- Objeto `Cliente` instanciado e persistido com sucesso
- Mensagem de erro clara em caso de falha de validação


## 👀 Observações
- O cliente é uma **Entidade Raiz (Aggregate Root)** no domínio
- Os telefones devem ser inseridos por meio de métodos do agregado para garantir consistência
- A data de inclusão pode ser definida no construtor ou atribuída via domínio ao criar a entidade