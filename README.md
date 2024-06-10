# Projeto Contador

#### Autor
- [Gabriel Garcia](https://github.com/GabrielGarciaUSP)

## Controle de Fluxo - Desafio

Este projeto consiste em uma aplicação Java simples que calcula o número de iterações através de dois parâmetros via terminal que representarão dois números inteiros, com estes dois números eu obtenho a quantidade de interações (for) e realizo a impressão no console (System.out.print) dos números incrementados, exemplo:

* Se você passar os números 12 e 30, logo teremos uma interação (for) com 18 ocorrências para imprimir os números, exemplo: `"Imprimindo o número 1"`, `"Imprimindo o número 2"` e assim por diante.
* Se o primeiro parâmetro for MAIOR que o segundo parâmetro, será lançado a exceção customizada chamada de `ParametrosInvalidosException` com a segunda mensagem: "O segundo parâmetro deve ser maior que o primeiro"   

## Estrutura do Projeto

O projeto é composto por uma única classe chamada `contador.java`, que contém toda a lógica necessária para a interação com o usuário e a exibição da mensagem final.


#### Importação da Classe Scanner

A classe Scanner é importada para permitir a leitura da entrada do usuário a partir do terminal.

```java
import java.util.Scanner;
```
#### Criação do Scanner

Uma instância da classe Scanner é criada para ler as entradas fornecidas pelo usuário.
```java
Scanner scanner = new Scanner(System.in);
```
#### Leitura dos Dados Inseridos
```java
int parametroUm = terminal.nextInt();
int parametroDois = terminal.nextInt();
```
Utilizamos essa função para receber o valor digitado pelo usuário e inseri-lo na variável.

#### Estrutura realizada para tratar a exceção 
```java
 try {
            // Chamando o método contendo a lógica de contagem
            contar(parametroUm, parametroDois);
        } catch (ParametrosInvalidosException e) {
            // Imprimir a mensagem: O segundo parâmetro deve ser maior que o primeiro
            System.out.println(e.getMessage());
        }
    static void contar(int parametroUm, int parametroDois) throws ParametrosInvalidosException {
        // Validar se parametroUm é MAIOR que parametroDois e lançar a exceção
        if (parametroUm >= parametroDois) {
            throw new ParametrosInvalidosException("O segundo parâmetro deve ser maior que o primeiro");
        }
}
class ParametrosInvalidosException extends Exception {
    public ParametrosInvalidosException(String mensagem) {
        super(mensagem);
    }
}

```
#### Fechamento do Scanner
```java
"scanner.close();"
```
#### Finalização

Por fim, imprimimos todos os dados conforme pedido na proposta do projeto.
```java
        for (int i = 1; i <= contagem; i++) {
            System.out.println("Imprimindo o número " + i);
        }
```
