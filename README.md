# NetMon

![Built with .NET](https://img.shields.io/badge/Built%20with-.NET%209.0-512BD4?logo=dotnet)
![Language](https://img.shields.io/badge/Language-C%23-239120?logo=c-sharp)
![Architecture](https://img.shields.io/badge/Architecture-Clean%20Code-blue)

**NetMon** é um jogo de estratégia e captura de criaturas baseado em linha de comando (CLI), desenvolvido em C# com .NET 9.0. O projeto simula um ecossistema onde jogadores atuam como treinadores, gerenciando inventário, explorando o ambiente e capturando monstros com diferentes níveis de raridade e atributos.

## Funcionalidades

O projeto vai além de um simples console app, implementando sistemas complexos de RPG:

* **Sistema de Captura Probabilístico:** Mecânica de captura que considera a força da "Rede" do jogador contra a agilidade e vida do "Monstro".
* **Gerenciamento de Entidades:**
    * **Monstros:** Classes com atributos detalhados (Força, Agilidade, Vida) e sistema de raridade (Comum, Raro, Lendário).
    * **Treinador:** Gestão de perfil e inventário do jogador.
* **Autenticação e Sessão:** Sistema de Login e Cadastro de usuários (`Usuario.cs`) para múltiplos jogadores.
* **Persistência de Dados:** Salvamento e carregamento automático do progresso e usuários utilizando serialização JSON.

## Tecnologias e Ferramentas

* **Linguagem:** C# (Recursos modernos do .NET 9).
* **Framework:** .NET 9.0 SDK.
* **Bibliotecas:** `Newtonsoft.Json` para manipulação de dados.
* **IDE:** Visual Studio / VS Code.

## Arquitetura e Padrões

O projeto foi estruturado utilizando uma solução modular para garantir a separação de responsabilidades e a escalabilidade do código:

* **Separação em Camadas (Multi-Project Solution):**
    * `ProjetoFinal.console`: Camada de Apresentação (UI), responsável pela interação com o usuário via terminal e fluxo do jogo.
    * `ProjetoFinal.modelos`: Biblioteca de Classes (Class Library) contendo a lógica de negócios, entidades (`Monstro`, `Treinador`, `Rede`) e enums (`Raridade`), totalmente desacoplada da interface.
* **POO (Programação Orientada a Objetos):** Uso extensivo de encapsulamento, herança e polimorfismo para modelar o comportamento das criaturas e itens.

## Habilidades Demonstradas

Este projeto serviu como laboratório para aprimorar competências essenciais de back-end:

* **Lógica de Programação Avançada:** Algoritmos para cálculo de taxas de sucesso e gerenciamento de estados do jogo.
* **Manipulação de Arquivos (File I/O):** Leitura e escrita de arquivos `.json` para persistência de dados complexos.
* **Arquitetura de Software:** Criação de soluções com múltiplos projetos e gerenciamento de dependências no .NET.
* **Modelagem de Dados:** Estruturação de classes e relacionamentos para representar um sistema de jogo coeso.

## Como Executar

1.  **Clone o repositório:**
    ```bash
    git clone [https://github.com/seu-usuario/netmon.git](https://github.com/seu-usuario/netmon.git)
    ```
2.  **Navegue até a pasta do projeto:**
    ```bash
    cd netmon
    ```
3.  **Restaure as dependências:**
    ```bash
    dotnet restore
    ```
4.  **Execute a aplicação:**
    ```bash
    dotnet run --project ProjetoFinal.console
    ```

---

### Estrutura de Arquivos

```text
NetMon/
├── ProjetoFinal.console/    # Interface do Usuário (Console)
│   ├── Program.cs           # Ponto de entrada e Loop do Jogo
│   └── usuarios.json        # Banco de dados local (Persistência)
├── ProjetoFinal.modelos/    # Regras de Negócio e Entidades
│   ├── Enums/
│   │   └── Raridade.cs
│   └── Modelos/
│       ├── Monstros.cs
│       ├── Rede.cs
│       ├── Treinador.cs
│       └── Usuario.cs
└── ProjetoFinal.sln         # Arquivo de Solução
