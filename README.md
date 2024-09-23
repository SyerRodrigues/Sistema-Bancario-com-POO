# Sistema Bancário em Python com POO

Este é um sistema bancário simples implementado em Python. Ele utiliza classes abstratas para gerenciar transações bancárias e mantém um histórico de transações para cada conta. O sistema suporta clientes físicos e operações de conta corrente com limites de saque.

## Funcionalidades

- Criar clientes físicos (Pessoa Física)
- Criar contas bancárias
- Realizar saques e depósitos
- Histórico de transações para cada conta
- Limites de saque diário para contas correntes

## Estrutura do Código

### Classes Principais

1. **Cliente**: Classe base para clientes, onde podem ser adicionadas contas.
2. **PessoaFisica**: Subclasse de `Cliente`, define o cliente do tipo pessoa física (CPF, nome e data de nascimento).
3. **Conta**: Define uma conta bancária, com saldo, número de conta, agência e histórico de transações.
4. **ContaCorrente**: Subclasse de `Conta`, permite saques com limite diário e um número máximo de saques.
5. **Transacao (abstract)**: Interface para transações. Implementada pelas classes de Saque e Depósito.
6. **Historico**: Armazena todas as transações de uma conta.

### Transações

As transações são implementadas através das classes abstratas `Saque` e `Deposito`. Cada transação é registrada no histórico da conta, com detalhes como o tipo, valor e data.

### Exemplo de Uso

```python
cliente = PessoaFisica(nome="João", data_nascimento="01/01/1980", cpf="123.456.789-10", endereco="Rua ABC")
conta = ContaCorrente.nova_conta(cliente, numero=1234)

conta.depositar(1000)
conta.sacar(200)
print(conta.historico.transacoes)
