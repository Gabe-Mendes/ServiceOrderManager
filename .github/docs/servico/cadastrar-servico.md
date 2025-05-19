# Caso de Uso: Cadastrar Serviço

## 🎯 Objetivo
Cadastrar um novo tipo de serviço que poderá ser selecionado em ordens de serviço.


## 📜 Regras de Negócio
- A descrição não pode estar vazia e deve ter no mínimo 3 caracteres
- A descrição deve ser única (não pode haver outro serviço ativo com a mesma descrição)
- O tempo estimado deve ser maior que zero
- O serviço é ativo por padrão ao ser cadastrado


## 🚨 Possíveis Erros
- Descrição duplicada
- Descrição inválida ou ausente
- Tempo de execução menor ou igual a zero


## 📥 Entrada
- `Descrição` (string, obrigatório) - Nome ou descrição do serviço prestado
- `Tempo de Execução Estimado` (inteiro, obrigatório) - tempo em minutos
- `Ativo` (boolean, opcional, default: true)


## 📤 Saída
- Objeto `Serviço` instanciado com sucesso
- Retorno de mensagem de erro informando a inconsistência dos dados


## 👀 Observações
- Serviços serão utilizados para compor ordens de serviço
- Pode haver serviços inativos no sistema para fins históricos, mas apenas os ativos devem estar disponíveis para seleção