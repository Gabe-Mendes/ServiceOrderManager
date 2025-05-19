# Caso de Uso: Consultar Telefones de um Cliente

## 🎯 Objetivo
Listar todos os telefones associados a um Cliente específico


## 📜 Regras de Negócio
- O cliente deve existir no sistema
- Listar todos os telefones ativos associados ao cliente
- Telefones são considerados ordenáveis (por tipo ou data de inclusão, se desejado — opcional)


## 🚨 Possíveis Erros
- Cliente não encontrado


## 📥 Entrada
- `IdCliente` (guid, obrigatório)


## 📤 Saída
- Lista de Objetos `Telefone` com os campos:
- `IdTelefone` (guid)
- `DDD` (inteiro)
- `Número` (string)
- `Tipo` (string — celular, residencial, comercial)
- `AceitaSMS` (bool)
- `AceitaWhatsApp` (bool)


## 👀 Observações
- Caso o cliente não possua telefones cadastrados, retornar uma lista vazia (não um erro)
- Pode ser interessante incluir filtros adicionais no futuro, como tipo de telefone ou preferências de contato