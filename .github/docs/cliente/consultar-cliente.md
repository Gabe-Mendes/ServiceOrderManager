# Caso de Uso: Consultar Cliente

## 🎯 Objetivo
Permitir a consulta de clientes cadastrados no sistema com base em uma busca textual parcial no nome.


## 📜 Regras de Negócio
- A busca deve ser case-insensitive
- Deve retornar todos os clientes cujo nome contenha o termo informado
- Clientes inativos podem ser retornados, conforme parâmetro adicional IncluirInativos: true


## 🚨 Possíveis Erros
- Termo de busca ausente ou com menos de 2 caracteres
- Nenhum cliente encontrado com o termo fornecido (retorna lista vazia)


## 📥 Entrada
- `Nome` (string, obrigatório) - termo parcial para busca
- `IncluirInativos` (boolean) - valor default como **FALSE**


## 📤 Saída
- Id
- Nome
- Ativo
- Data de Inclusão


## 👀 Observações
- A busca deve ser otimizada para grandes volumes de dados (uso de índice, se aplicável)
- Esse caso de uso não deve retornar dados sensíveis além do necessário
- Pode ser utilizado em autocomplete ou telas de pesquisa no sistema