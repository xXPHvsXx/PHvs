# Projeto: Sistema de Gestão de Funcionários de Restaurante

Este projeto em Python demonstra a aplicação de conceitos de Programação Orientada a Objetos (POO) em um cenário de gerenciamento de funcionários de um restaurante.

## Conceitos Aplicados

1.  **Interface (Classe Abstrata):**
    * A classe `IFuncionario` (utilizando `abc.ABC`) atua como uma interface. Ela define um "contrato" com métodos abstratos (`calcular_salario` e `obter_descricao_cargo`) que todas as classes de funcionários devem obrigatoriamente implementar. Isso garante que todo funcionário terá uma forma de calcular seu salário e descrever seu cargo.

2.  **Classes Concretas:**
    * As classes `Chef` e `Garcom` são implementações concretas da interface `IFuncionario`. Cada uma delas fornece sua própria lógica para os métodos abstratos.
    * O `Chef` calcula o salário somando um bônus ao salário base.
    * O `Garcom` calcula o salário somando as gorjetas ao salário base.

3.  **Polimorfismo:**
    * O polimorfismo é demonstrado na função `processar_folha_pagamento`. Esta função recebe uma lista de funcionários (`list[IFuncionario]`).
    * Dentro do loop, a função chama `funcionario.calcular_salario()` em cada objeto. O Python, em tempo de execução, determina qual versão do método `calcular_salario` deve ser chamada (a da classe `Chef` ou a da classe `Garcom`), dependendo do tipo real do objeto.
    * Isso permite tratar objetos de diferentes classes de maneira uniforme, tornando o código mais limpo, flexível e fácil de estender (se um novo tipo de funcionário, como `Gerente`, for adicionado, a função `processar_folha_pagamento` não precisará ser alterada).

## Como Executar o Projeto

1.  Certifique-se de ter o Python instalado.
2.  Salve o código acima em um arquivo chamado `main.py`.
3.  Execute o arquivo pelo terminal:
    ```bash
    python main.py
    ```

A saída mostrará a descrição de cada funcionário, seu salário calculado e o custo total da folha de pagamento.