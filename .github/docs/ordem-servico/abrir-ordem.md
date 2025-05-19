# Caso de Uso: Abrir Ordem de Serviço

## 🎯 Objetivo
Registrar a abertura de uma nova ordem de serviço vinculada a um cliente e a um serviço.


## 📜 Regras de Negócio
- Cliente e Serviço informados devem existir e estar **ativos**
- Não é permitido abrir uma ordem de serviço com data futura
- Uma ordem é criada com status **Ativa** e **sem data de encerramento**


## 🚨 Possíveis Erros
- Cliente não encontrado ou inativo
- Serviço não encontrado ou inativo
- Data de abertura inválida (futura)


## 📥 Entrada
- `IdCliente` (guid, obrigatório)
- `IdServico` (guid, obrigatório)
- `Data de Abertura` (datetime, opcional - default: data hora atual)
- `Observações` (string, opcional)


## 📤 Saída
- Objeto `OrdemServico` criado com `Id`, `IdCliente`, `IdServico`, `DataAbertura`, `Status`: `Ativo`


## 👀 Observações
- O relacionamento entre cliente e serviço é estabelecido apenas no momento da abertura
- Ordens de serviço devem ser encerradas explicitamente em outro caso de uso
- Ordens podem futuramente conter histórico de alterações e observações complementares