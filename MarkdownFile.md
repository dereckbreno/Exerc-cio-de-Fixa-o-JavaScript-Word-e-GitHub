Exercício de Fixação JavaScript

Nome: Dereck Breno da silva fernandes

Data: 20/09/2025

### 2.1 Variáveis e Tipos

*   **Qual a diferença entre var, let e const?**  
    
*   **var**:
    *   **Escopo de Função/Global**: Ignora blocos como if e for. É visível em toda a função ou globalmente.
    *   Permite reatribuição e redeclaração (o que pode levar a erros).
    *   É a forma mais antiga e menos recomendada para códigos novos.
*   **let**:
    *   **Escopo de Bloco** ({}): A variável só existe dentro do bloco onde foi declarada (ex: dentro de um if, for ou um par de chaves solto).
    *   Permite reatribuição (mudar o valor).
    *   **NÃO** permite redeclaração no mesmo escopo.
    *   É ideal para variáveis que **precisam ter seu valor alterado**.
*   **const**:
    *   **Escopo de Bloco** ({}): Igual ao let.
    *   **NÃO** permite reatribuição (é uma constante, seu valor não pode ser alterado depois de inicializado).
    *   **NÃO** permite redeclaração.
    *   **Deve ser inicializada** no momento da declaração.
    *   É a escolha **preferencial** para a maioria das variáveis, a menos que você saiba que o valor precisará mudar.

**Boa Prática:**

Para a maioria dos projetos JavaScript modernos, a recomendação é usar:

*   **const** por padrão.
*   **let** apenas se você souber que o valor da variável será alterado (por exemplo, em contadores de _loop_ ou variáveis que armazenam estados mutáveis).
*   **Evitar o uso de var** em códigos novos devido ao seu escopo confuso (escopo de função/global).
*   **Liste os tipos primitivos do JavaScript com exemplos.  
    **

Os tipos de dados primitivos em JavaScript são:

1.  **String**: Para dados textuais (ex: "olá", 'mundo').
2.  **Number**: Para números inteiros e de ponto flutuante (ex: 10, 3.14).
3.  **Boolean**: Para valores lógicos, apenas true (verdadeiro) ou false (falso).
4.  **Null**: Representa a ausência intencional de valor (ex: null).
5.  **Undefined**: Indica que uma variável foi declarada, mas ainda não recebeu um valor (ex: let x;).
6.  **Symbol**: (ES6) Para valores únicos e imutáveis.
7.  **BigInt**: (ES2020) Para números inteiros muito grandes, que excedem o limite do tipo Number.

O tipo **Object** (que inclui arrays, funções, etc.) **não é primitivo**, é um tipo de referência.

*   **Qual a diferença entre null e undefined?**

1\. undefined (Não definido)

O undefined é o estado padrão para qualquer variável que foi declarada, mas ainda não recebeu um valor.

Exemplo de ocorrência:

JavaScript

let nome; // Variável declarada, mas não inicializada.

console.log(nome); // Saída: undefined

let objeto = {};

console.log(objeto.propriedadeInexistente); // Saída: undefined

#### 2\. null (Nulo)

O null é um valor que você, como programador(a), atribui intencionalmente a uma variável para indicar que ela está vazia, ou seja, que não está apontando para nenhum objeto ou valor válido. É usado para "limpar" ou redefinir uma variável.

Exemplo de ocorrência:

JavaScript

let usuarioLogado = { nome: "Ana" };

// ... depois do logout ...

usuarioLogado = null; // Atribuição intencional para indicar que não há mais usuário.

console.log(usuarioLogado); // Saída: null

### Qual usar?

*   Use null para indicar a ausência intencional de um valor.
*   Deixe que o undefined seja usado pelo motor JavaScript (por exemplo, quando a variável ainda não foi inicializada).
*   **Explique == e ===.**

### 1\. == (Igualdade Abstrata)

*   **O operador == compara apenas se os valores são equivalentes. Se os operandos forem de tipos diferentes, o JavaScript tenta converter (coerção) um ou ambos para um tipo comum antes de realizar a comparação.**

### 2\. === (Igualdade Estrita)

*   **O operador === compara se os operandos são iguais em valor E em tipo de dado. Nenhuma coerção de tipo é realizada.**
*   **Para que a comparação retorne true, tanto o valor quanto o tipo devem ser idênticos.**
*   **Este operador é considerado a boa prática no JavaScript por ser previsível e evitar os "erros silenciosos" causados pela coerção de tipo.**

### 2.2 Operadores e Expressões

| Operador | Nome | Função | Exemplo | Resultado |
| --- | --- | --- | --- | --- |
| + | Adição | Soma dois valores. | 5 + 3 | 8 |
| - | Subtração | Subtrai o segundo valor do primeiro. | 10 - 4 | 6 |
| * | Multiplicação | Multiplica dois valores. | 6 * 7 | 42 |
| / | Divisão | Divide o primeiro valor pelo segundo. | 20 / 5 | 4 |
| Operador | Nome | Função | Exemplo | Resultado |
| --- | --- | --- | --- | --- |
| % | Módulo | Retorna o resto da divisão. | 10 % 3 | 1 |
| **** | Exponenciação | Retorna o resultado da potência. | 2 ** 3 | 8 |
| ++ | Incremento | Adiciona 1 à variável (pode ser prefixado ou postfixado). | let x = 5; x++ | x é 6 |
| -- | Decremento | Subtrai 1 da variável (pode ser prefixado ou postfixado). | let y = 5; y-- | y é 4 |

#### 

#### 1\. && (AND Lógico)

*   Se o primeiro operando for "falso" (_falsy_), ele retorna o primeiro operando e nem avalia o segundo.
*   Se o primeiro operando for "verdadeiro" (_truthy_), ele retorna o segundo operando.

// Exemplo com valores (não booleanos):

let nome = "Alice";

let padrao = "Visitante";

let usuario = nome && padrao;

// Como "Alice" é truthy, retorna o segundo valor.

console.log(usuario); // Saída: "Visitante"

#### 2\. || (OR Lógico)

*   Se o primeiro operando for "verdadeiro" (_truthy_), ele retorna o primeiro operando e nem avalia o segundo.
*   Se o primeiro operando for "falso" (_falsy_), ele retorna o segundo operando.

// Exemplo comum para definir valor padrão:

let usuarioLogado = null; // null é falsy

let nomeExibido = usuarioLogado || "Convidado";

// Como null é falsy, retorna o segundo valor.

console.log(nomeExibido); // Saída: "Convidado"

*   Preveja os resultados:

"5" + 2  
JavaScript  
let resultado1 = "5" + 2;

// Saída prevista: "52"

_(Explicação: O operador + com uma String (o "5") força o JavaScript a tratar o 2 como uma string também, realizando a concatenação.)_

true + 1  
JavaScript  
let resultado2 = true + 1;

// Saída prevista: 2

_(Explicação: Em um contexto de operação matemática, o true é coagido para o valor numérico 1, resultando em 1 + 1 = 2.)_

### 2.3 Estruturas de Controle

### 1\. if (Se)

O bloco if é o ponto de partida e testa a primeira condição. O código dentro do if só será executado se a condição avaliada for **verdadeira** (true).

#### Estrutura:

JavaScript

if (condição) {

// Código a ser executado SE a condição for verdadeira.

}

#### Exemplo:

JavaScript

let idade = 20;

if (idade >= 18) {

console.log("Você é maior de idade e pode entrar.");

}

// Saída: Você é maior de idade e pode entrar.

### 2\. else if (Senão, Se)

O bloco else if é opcional e é usado para testar uma **segunda condição** ou qualquer condição subsequente, **somente se a condição anterior (do if ou de um else if anterior) for falsa**.

Você pode ter quantos blocos else if forem necessários.

#### Estrutura:

JavaScript

if (condição1) {

// ...

} else if (condição2) {

// Código a ser executado SE a condição1 for Falsa E a condição2 for Verdadeira.

}

#### Exemplo:

JavaScript

let hora = 14;

if (hora < 12) {

console.log("Bom dia!");

} else if (hora < 18) {

console.log("Boa tarde!");

} // 14 é maior que 12, então entra neste bloco.

// Saída: Boa tarde!

### 3\. else (Senão)

O bloco else também é opcional e é o "caminho padrão". Ele será executado **somente se todas as condições anteriores (if e todos os else ifs) forem falsas**.

Ele não recebe nenhuma condição, pois sua função é cobrir todos os outros casos.

#### Estrutura:

JavaScript

if (condição1) {

// ...

} else if (condição2) {

// ...

} else {

// Código a ser executado SE NENHUMA das condições anteriores for verdadeira.

}

#### Exemplo Completo:

JavaScript

let nivel = "admin";

if (nivel === "convidado") {

console.log("Acesso limitado.");

} else if (nivel === "usuario") {

console.log("Acesso padrão.");

} else if (nivel === "admin") {

console.log("Acesso total.");

} else {

console.log("Nível de acesso desconhecido.");

}

// Saída: Acesso total.

Se alterarmos nivel para, digamos, "desconhecido", a execução pulará o if e os dois else ifs e cairá no else:

JavaScript

let nivel = "desconhecido"; // Alteração

if (nivel === "convidado") {

console.log("Acesso limitado.");

} else if (nivel === "usuario") {

console.log("Acesso padrão.");

} else if (nivel === "admin") {

console.log("Acesso total.");

} else {

console.log("Nível de acesso desconhecido.");

}

// Saída: Nível de acesso desconhecido.

*   Como usar switch?

O switch é uma alternativa ao uso de múltiplas estruturas if...else if. Ele avalia uma única expressão e compara seu valor com uma lista de possíveis valores (cases).

*   **Estrutura**: switch (expressão) é seguido por vários blocos case valor: e, opcionalmente, um bloco default.
*   **Comparações**: Usa igualdade estrita (===) para comparar a expressão com cada case.
*   **break**: É crucial usar a palavra-chave break após o código de cada case para evitar que a execução continue para o próximo case (comportamento chamado _fall-through_).

Escreva um exemplo de verificação de maioridade5.

JavaScript

let idade = 20;

const idadeMinima = 18;

if (idade >= idadeMinima) {

console.log("Acesso concedido. Você é maior de idade.");

} else {

console.log("Acesso negado. Você é menor de idade.");

}

2.4 Loops e Repetições 6

Liste os tipos de loops: for, while, do...while7.

*   **for**: Usado quando o número de iterações é conhecido. Possui uma inicialização, uma condição e um incremento/decremento definidos na mesma linha.
*   **while**: Executa um bloco de código repetidamente **enquanto** uma condição especificada for true. A condição é checada antes de cada iteração.
*   **do...while**: Executa um bloco de código pelo menos uma vez e, em seguida, repete a execução **enquanto** uma condição especificada for true. A condição é checada após a primeira iteração.

Escreva mentalmente como imprimir números de 1 a 58.

JavaScript

for (let i = 1; i <= 5; i++) {

console.log(i);

}

// Saída mental: 1, 2, 3, 4, 5

Explique break e quando usá-lo9.

*   **Explicação**: O comando break é usado para **sair imediatamente** de um loop (for, while, do...while) ou de uma estrutura switch, interrompendo o fluxo normal de execução.
*   **Quando usar**: É usado quando uma condição desejada é atingida e não é necessário continuar com as iterações restantes do loop. Por exemplo, em uma busca, se o item for encontrado, o break economiza processamento.

2.5 Funções 10

O que é uma função? 11

Uma função é um bloco de código reutilizável projetado para executar uma tarefa específica. Ela pode aceitar zero ou mais valores de entrada (parâmetros) e pode retornar um valor de saída.

Diferença entre função declarada e função expressa12.

| Característica | Função Declarada (function nome() {}) | Função Expressa (const nome = function() {}) |
| --- | --- | --- |
| Hoisting | Sofre hoisting: pode ser chamada antes de ser definida no código. | Não sofre hoisting: só pode ser chamada após ser definida. |
| Sintaxe | Começa com a palavra-chave function seguida pelo nome. | É atribuída a uma variável (usando const, let ou var). |

Crie uma função que recebe um nome e retorna saudação13.

JavaScript

function saudacao(nome) {

return "Olá, " + nome + "! Bem-vindo(a).";

}

// Exemplo de uso:

console.log(saudacao("Beatriz")); // Saída: Olá, Beatriz! Bem-vindo(a).

2.6 Mini-casos práticos 14

Verificação de número par ou ímpar15.

JavaScript

function verificarParImpar(numero) {

if (numero % 2 === 0) { // O resto da divisão por 2 é 0 para números pares.

return "Par";

} else {

return "Ímpar";

}

}

console.log(verificarParImpar(7)); // Saída: Ímpar

console.log(verificarParImpar(10)); // Saída: Par

Criação mental de uma lista de compras (array)16.

JavaScript

const listaDeCompras = \[

"Pão",

"Leite",

"Ovos",

"Manteiga",

"Café"

\];

console.log(listaDeCompras\[1\]); // Saída: Leite

Somar números de 1 a 10 usando loop17.

JavaScript

let soma = 0;

for (let i = 1; i <= 10; i++) {

soma = soma + i; // ou soma += i;

}

console.log("A soma de 1 a 10 é:", soma); // Saída: A soma de 1 a 10 é: 55

2.7 Reflexão 18

Por que conhecer tipos e operadores ajuda a programar melhor? 19

Conhecer tipos de dados (String, Number, Boolean, etc.) e operadores (+, ==, ===) é essencial porque:

*   **Previne Bugs:** Permite prever e evitar a coerção de tipos indesejada (ex: usando === em vez de ==) e erros de tipo em operações (ex: tentar somar uma string com um número e obter concatenação).
*   **Otimiza o Uso da Memória:** Ajuda a escolher a estrutura de variável mais adequada (const para valores fixos, let para mutáveis).
*   **Clareza do Código:** Garante que as operações lógicas e matemáticas funcionem como o esperado.

Por que usar console.log() é importante para debug? 20

O console.log() é a ferramenta mais básica e essencial para a depuração, pois:

*   **Rastreia o Fluxo:** Permite ver em qual linha ou bloco de código o programa está sendo executado.
*   **Inspeciona Variáveis:** Exibe o valor exato de variáveis em um ponto específico da execução, ajudando a identificar quando e onde um valor inesperado foi atribuído.
*   **Validação de Condição:** Ajuda a confirmar se as condições (if, while) estão sendo avaliadas como true ou false corretamente.

Como planejar variáveis, funções e loops antes de programar? 21

Planejar é crucial e geralmente envolve as seguintes etapas:

*   **Variáveis**:
    *   **Propósito**: O que este dado precisa armazenar? (Ex: Nome do usuário, pontuação, status).
    *   **Tipo**: Qual o tipo de dado? (String, Number, Boolean).
    *   **Mutabilidade**: O valor mudará? (Se não, use const; se sim, use let).
*   **Funções**:
    *   **Responsabilidade Única**: O que exatamente esta função deve fazer? (Ex: Calcular imposto, formatar data).
    *   **Entrada/Saída**: Quais dados ela precisa receber (parâmetros) e qual dado ela deve retornar?
*   **Loops**:
    *   **Iterações**: Quantas vezes ou em qual condição o bloco de código deve se repetir?
    *   **Condição de Saída**: Qual é a condição que garante que o loop terminará para evitar um _loop_ infinito? (Essencial para loops while).