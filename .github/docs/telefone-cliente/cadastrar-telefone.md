# Caso de Uso: Cadastrar Telefone

## 🎯 Objetivo
Cadastrar um número de telefone associado a um cliente, com validação de formato e regras de negócio.


## 📜 Regras de Negócio
- O DDD deve conter 2 dígitos válidos (ex: 11, 21, 85)
- O número do telefone deve conter 8 ou 9 dígitos
- O tipo deve ser um dos seguintes: `celular`, `residencial`, `comercial`
- Telefones do tipo `residencial` ou `comercial` não podem aceitar SMS ou WhatsApp
- Telefones são objetos imutáveis — alterações implicam substituição completa


## 🚨 Possíveis Erros
- DDD inválido
- Número fora do padrão
- Tipo de telefone inválido
- Regras inconsistentes com o tipo (ex: aceitar WhatsApp em telefone residencial)


## 📥 Entrada
- `DDD` (inteiro, obrigatório, 2 dígitos)
- `Número` (string, obrigatório, 8 ou 9 dígitos)
- `Tipo` (string, obrigatório, opções fixas - celular/residencial/comercial)
- `AceitaSMS` (bool, obrigatório, `true` ou `false`)
- `AceitaWhatsApp` (bool, obrigatório, `true` ou `false`)


## 📤 Saída
- Objeto `Telefone` instanciado com sucesso
- Retorno de mensagem de erro informando a inconsistência dos dados


## 👀 Observações
- Um cliente pode possuir mais de um telefone (relacionamento 1:N)
- O telefone é um **Value Object** no domínio