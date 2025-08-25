# Singleton - Creational (Criação)

## Intenção

*Garantir que uma classe tenha somente uma instância no programa e fornecer um ponto de acesso global para a mesma.*

---

## Destilando a intenção

O Singleton é um padrão de projeto que tem a intenção de resolver dois problemas em uma aplicação:

- **Garantir que uma classe tenha somente uma instância no programa** - isso é muito comum para programas que acessam recursos compartilhados, como bases de dados, sistemas de arquivos, interfaces gráficas, spoolers de impressão, módulos de um programas e mais.
- **Fornecer um ponto de acesso global para a mesma** - isso deixa o singleton muito mais paprecido com variáveis globais, porque
temos um único objeto, com acesso global, sendo usado por várias partes da aplicação.

Apesar de ser um dos padrões mais usados na atualizdade, requer conhecimento e cuidado ao utilizá-lo. Um programador pode facilmente
criar um Singleton que gera problemas de concorrência em um programa.

Note que o Singleton tem duas responsabilidade e isso quebra a regra do SRP (Single Responsibility Principle).

---

## Estrutura 

Veja a pasta diagramas.

## Aplicabilidade

- User o singleton quando uma classe precisa ter somoente uma instância disponível em todos o seu programa;
- User o singleton quando perceber que está usando variáveis globais para manter partes importantes do programa, como variáveis de configuração que são usadas por toda a aplicação.

## Implementação - Teoria

Isso popde mudar de linguarem para linguagem, em Python sera de uma maneira, em JavaScript de outra e em linguarem com tipagem estática, como TypeScript, de outra. Mas o senso comum sobre singletons é o seguinte:

- Declarar um campo na classe para armazenar a instância do Singleton.
- Declarar um método público (getter) para obter a instância do Singleton;
- Na chamada do método público, adicione *lazy instantiation*, ou seja, verifique se uma instância do Singleton já foi criada; se foi, retorne-a, se não crie uma nova instância e retorne-a.
- Não permita que novas instâncias da classe. Você pode atingir facilmente este objetivo fazendo o construtor da classe privado.

## Consequências

O que é bom ou ruim nos Singletons:

**Bom:**
- Acesso controlado por encapsulamento à instância única;
- É possível permitir um número variável de instâncias (pode soar estranho, mas é possível criar um Singleton que permite n instâncias de uma classe);
- É possível usar thead lock para garantir que duas partes do código não alterem o singleton simultaneamente;
- Usa *lazy instatiation*, ou seja, o Singleton só será instanciado no momento do uso;

**Ruim:**
- É mais difícil de testar;
- Viola o princípio de responsabilidade única;
- Requer tratamento especial em casos de concorrência;