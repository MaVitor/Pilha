# Implementação de Pilha em Java

## Sobre o Projeto
Este repositório contém a implementação de uma estrutura de dados do tipo **Pilha** utilizando Java. O projeto inclui uma interface genérica para pilhas, uma implementação baseada em vetor dinâmico e um conjunto de testes que avaliam diferentes estratégias de crescimento do vetor.

## Estrutura do Código
O projeto é composto pelos seguintes arquivos:

### 1. **Interface Pilha (`Pilha.java`)**
Define a estrutura básica de uma pilha, incluindo os seguintes métodos:
- `size()`: Retorna o tamanho da pilha.
- `isEmpty()`: Verifica se a pilha está vazia.
- `top()`: Retorna o elemento do topo sem removê-lo.
- `push(Object o)`: Adiciona um elemento ao topo.
- `pop()`: Remove e retorna o elemento do topo.

### 2. **Classe de Exceção (`PilhaVaziaExcecao.java`)**
Uma exceção personalizada para indicar tentativas de operação em uma pilha vazia.

### 3. **Implementação da Pilha (`PilhaVetor.java`)**
Esta classe implementa a interface `Pilha` usando um **vetor dinâmico**. Alguns destaques da implementação:
- O vetor cresce dinamicamente sempre que está cheio.
- Dois modos de crescimento são suportados:
  - **Incremento fixo**: O vetor cresce de um tamanho predefinido.
  - **Duplicação**: O vetor dobra de tamanho a cada realocação.
- Os seguintes métodos são implementados:
  - `push(Object o)`: Insere um elemento no topo da pilha.
  - `pop()`: Remove e retorna o elemento do topo.
  - `top()`: Retorna o elemento do topo sem removê-lo.
  - `size()`: Retorna o tamanho atual da pilha.
  - `isEmpty()`: Retorna `true` se a pilha estiver vazia.
  - `empty()`: Esvazia completamente a pilha.

### 4. **Testes de Desempenho (`TestePilha.java`)**
A classe `TestePilha` executa testes para medir o desempenho da pilha com diferentes estratégias de crescimento. Os testes avaliam:
- Crescimento fixo (incremento de 10 elementos por vez).
- Crescimento por **duplicação** (o vetor dobra de tamanho sempre que atinge sua capacidade).
- Tempo de inserção para diferentes quantidades de elementos: `10`, `100`, `1000`, `10000`, `100000`, `1000000`.

## Como Compilar e Executar

1. **Compilar todos os arquivos**:
```sh
javac *.java
```

2. **Executar os testes**:
```sh
java TestePilha
```

## Exemplo de Uso
Abaixo está um exemplo simples de como utilizar a pilha no seu código:

```java
public class Main {
    public static void main(String[] args) {
        Pilha pilha = new PilhaVetor(5, 10); // Pilha com capacidade inicial 5 e crescimento de 10
        
        pilha.push("A");
        pilha.push("B");
        pilha.push("C");
        
        System.out.println("Topo: " + pilha.top()); // Saída: C
        System.out.println("Removendo: " + pilha.pop()); // Saída: C
        System.out.println("Novo topo: " + pilha.top()); // Saída: B
    }
}
```

---

