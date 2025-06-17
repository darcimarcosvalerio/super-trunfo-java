# super-trunfo-java
Estacio_super-trunfo-java
# Desafio: Jogo Super Trunfo em Java

Este repositório contém a implementação do jogo clássico "Super Trunfo" em Java, desenvolvido como parte do desafio da disciplina.

## 🎯 Objetivo do Projeto

O objetivo deste projeto é simular o funcionamento de um jogo de cartas Super Trunfo, onde jogadores (um humano e um ou mais computadores) comparam atributos de suas cartas para tentar ganhar as cartas dos oponentes. O jogo lida com a distribuição de cartas, turnos dos jogadores, comparação de atributos e o gerenciamento das cartas ganhas, incluindo o tratamento de empates.

## ✨ Funcionalidades Implementadas

* **Criação de Cartas Dinâmicas:** Cartas podem ser criadas com um nome e múltiplos atributos numéricos (ex: Velocidade, Potência, Peso).
* **Baralho:**
    * Adicionar cartas ao baralho.
    * Embaralhar o baralho.
    * Distribuir cartas entre os jogadores.
    * Puxar cartas do topo.
* **Jogadores:**
    * Gerenciar a mão de cartas de cada jogador.
    * Permitir que um jogador jogue a carta do topo de sua mão.
* **Lógica do Jogo:**
    * Alternância de turnos entre os jogadores.
    * O jogador da vez escolhe o atributo para comparação.
    * Comparação das cartas em jogo com base no atributo escolhido.
    * O vencedor da rodada recolhe as cartas jogadas.
    * **Tratamento de Empates:** Em caso de empate na rodada, as cartas são colocadas em um "pote" e o vencedor da próxima rodada leva todas as cartas do pote. O jogador que escolheu o atributo no empate permanece como jogador atual.
    * Condição de vitória: O último jogador com cartas restantes vence o jogo.
* **Interface de Console:** Interação simples através do terminal para jogar.

## 📁 Estrutura do Projeto

O projeto está organizado nas seguintes classes Java:

* `Carta.java`: Define a estrutura de uma carta, incluindo seu nome e um mapa de atributos (String -> Double). Contém métodos para adicionar atributos, exibi-los e comparar duas cartas por um atributo específico.
* `Baralho.java`: Representa o baralho de cartas. Possui métodos para adicionar cartas, embaralhar e distribuir cartas aos jogadores.
* `Jogador.java`: Define um jogador, que possui um nome e uma mão de cartas. Contém métodos para adicionar, remover e verificar a quantidade de cartas em sua mão.
* `Jogo.java`: Contém a lógica principal do jogo. Orquestra a configuração, o fluxo de turnos, a comparação de cartas, o tratamento de vitórias/empates e o fim do jogo. Possui o método `main` para iniciar a aplicação.

## 🚀 Como Compilar e Rodar

Siga os passos abaixo para baixar, compilar e executar o projeto em sua máquina:

1.  **Clone o Repositório:**
    ```bash
    git clone [https://github.com/](https://github.com/)<seu-usuario>/super-trunfo-java.git
    ```
    Substitua `<seu-usuario>` pelo seu nome de usuário do GitHub.

2.  **Navegue até a Pasta do Projeto:**
    ```bash
    cd super-trunfo-java
    ```

3.  **Compile os Arquivos Java:**
    Certifique-se de ter o Java Development Kit (JDK) instalado.
    ```bash
    javac Carta.java Baralho.java Jogador.java Jogo.java
    ```

4.  **Execute o Jogo:**
    ```bash
    java Jogo
    ```

    O jogo será executado no seu terminal, e você poderá interagir com ele seguindo as instruções na tela.

## 📝 Como Adicionar/Modificar Cartas

Você pode facilmente adicionar ou modificar as cartas do jogo no método `main` da classe `Jogo.java`.

Exemplo:
```java
// Dentro do método main da classe Jogo.java
Baralho baralhoDoJogo = new Baralho();

// Criando uma nova carta de carro
Carta minhaNovaCarta = new Carta("Carro Incrível");
minhaNovaCarta.adicionarAtributo("Velocidade", 450.0);
minhaNovaCarta.adicionarAtributo("Potencia", 1800.0);
minhaNovaCarta.adicionarAtributo("Peso", 1000.0);
baralhoDoJogo.adicionarCarta(minhaNovaCarta);

// Modificando uma carta existente (se já tiver sido adicionada, você teria que buscá-la ou recriar)
// Para o propósito de exemplo, vamos criar uma nova e adicionar
Carta outraCarta = new Carta("Moto Veloz");
outraCarta.adicionarAtributo("Velocidade", 300.0);
outraCarta.adicionarAtributo("Cilindrada", 1000.0); // Novo atributo
baralhoDoJogo.adicionarCarta(outraCarta);
