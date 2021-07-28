# <span style="text-transform: uppercase; color: #D00; font-weight: bold">Trabalho ainda em progresso. Revisão necessária.</span>

# História do Javascript

- **Lançado em setembro de 1995** - Foi lançado juntamente com a versão beta do navegador NetScape e o projeto foi lançado inicialmente com o nome de Mocha, depois ele passou a ser Livescript e por fim foi chamado de Javascript. A alteração de Livescript pra Javascript, ocorreu em um anuncio conjunto com a Sun MicroSystem em Dezembro de 1995. 

  A Sun MicroSystem foi onde a linguagem Java surgiu, mais especificamente em maio de 1995. Em uma equpe liderada por James Goslin, que para muitos é considerado o pai da linguagem Java.

  Essa mudança coincidiu com a época que o NetScape adcionou suporte ao Java em seu navegador, por meio de aplets.

  Essa mudança de Livescript pra Javascipt, causou duvida em muitas pessoas, porque muita gente achava que Javascript era baseado em Java, mas na verdade, pra muitos isso é uma estratégia de marketing da linguagem Javascript, pra aproveitar o lançamento da linguagem Java.

- **Criado por Brendan Eich** - nascido em 1961 nos Estados Unidos, trabalhou durante um bom tempo em sistemas operacionais e sistemas de rede, escrevendo micro kernels e códigos pra DSPS.

  DSPS são processadores de sinais digitais.

  Ele ficou conhecido por seu trabalho na Netscape e na Mozilla.

  Na Netscape, ele começou a trabalhar em Abril de 1995 com o Javascript, depois ajudou na fundação da Mozilla.org em 1998, atuando como arquiteto chefe.

- **ECMAScript** - o Netscape submeteu as especificações do Javascript pra padronização do orgão que se chama Ecma International. Esse trabalho na especificação foi chamado de Ecma 262 e começou em Novembro de 1996, foi assim que surgiu o ECMAScript. 

  Ele é uma especificação da linguagem de programação que é padronizado pelo Ecma 262 da Ecma International. Servindo como base pra futuras incrementações de outras linguagens Scripts, como: Javascript, JScript e ActionScript.

- **TC39** - é o comitê responsável pela evolução do Javascript, seus colaboradores, em maioria, são integrantes dos browsers atuais, seja Mozilla, Edge ou Google Chrome. Eles se reunem regularmente e nesses encontros eles discutem as propostas pro ECMAScript.

  Vale ressaltar que nesses encontros nenhuma decisão é forte o bastante pra fazer uma proposta ser negada. O que faz uma proposta ser aceita é a maioria dos votos entre eles.

  O TC39, vem pra manter e atualizar os padrões do ECMAScript que é no projeto Ecma 262 e ele identifica, desenvolve e mantem padrões pras bibliotecas que estendem as features do ECMAScript, que é o: ECMA 402. E ele desenvolve suits de testes para que as propostas possam ser testadas. Esse projeto se chama ECMA TR104.

  Link do Github do TC39: https://github.com/tc39

  Link do repositório de propostas: https://github.com/tc39/proposals

  

  ## Fluxo de proposta

  - **Stage 0: strawman -** Um formulário será submetido com a ideia de evoluir o ECMAScript. Essas submissões devem ser feitas por um membro ou contribuidor registrado no TC39.

    **O que é obrigatório nessa etapa:** O documento precisa ser revisado no encontro da TC39 e depois deve ser adcionado as páginas da proposta como stage 0.

  - **Stage 1: proposal -** É nessa etapa que surge a proposta formal da funcionalidade.

    **O que é obrigatório nessa etapa:** Nessa etapa um campeão ou um co-campeão será encarregado da proposta e ele precisa ser membro do TC39. 

    Necessário ser bem descrito o objetivo da proposta e ter exemplos.

    É possível que haja várias alterações na proposta, nessa etapa.

  - **Stage 2: draft -** Primeira versão da proposta que vai entrar na especificação.

    **O que é obrigatório nessa etapa:** A proposta precisa ter uma descrição formal da sintaxe e semântica da funcionalidade. A descrição precisa ser o mais completo possível.

    Nesse momento, duas implementações são necessárias nessa proposta, sendo que uma delas pode rodar pelo Babel. E o próximo passo que pode vir é ter alterações incrementais nessa proposta.

  - **Stage 3: candidate -** A proposta está quase finalizada, e agora ela vai precisar de um feedback de implementação de usuários para progredir. A especificação deve estar completa nessa etapa. 

    Será feita algumas revisões da TC39, que não podem ser revisões feitas pelo campeão responsável, e o editor da especificação do ECMAScript precisa assinar essa especificação.

    **O que é obrigatório nessa etapa:** Nesse momento ela deve ter pelo menos duas implementações compátiveis com a especificação.

    A proposta pode sofrer alterações por questões críticas levantadas pelo feedback de uso dela

  - **Stage 4: finished -** A proposta está pronta para ser incluída na especificação.

    **O que é obrigatório nessa etapa:** Ela deve passar pela suit de testes. 

    Ter duas implementações de conformidade com a especificação que passa no teste. 

    Ter uma experiência prática e significativa na implementação, baseado no feedback do stage 3. 

    O editor da especificação do ECMAScript deve assinar o texto dessa especificação.

***

# Conceitos do Javascript

- **Linguagem interpretada -** O código é executado de cima para baixo e o resultado da execução é imediatamente retornado. Não há necessidade de compilar o código antes do navegador executar.
- **Linguagem de tipagem fraca e dinâmica** 
  - **Fraca** pois não há verificação em todas as operações do Javascript. É possível concatenar variáveis com tipos diferentes, sem que ocorra um erro.
  - **Dinâmica** pois não há necessidade de explicitar o tipo da variável no momento de sua criação.

- **Funções de primeira classe e de ordem maior -** A função pode ser atribuída a uma variável; atribuída a uma estrutura de dados, seja um object ou um array; pode ser passada por argumentos e até retornada por outras funções.

Exemplo:

````javascript
function getName() {
    return 'Pablo L. S. Marinho';
}

function logFn(Fn) {
    console.log(fn());
}

const logFnResult = logFn;

logFnResult(getName); //Passando a função getName por argumento
````

***

- **Closure -** Também conhecido como escopo léxico, é a capacidade de uma função lembrar do ambiente em que ela foi criada.

Exemplo:

````javascript
function init() {
    const exemplo = 'Essa variável';
    
    return function() {
        console.log('1 - O valor da variável exemplo é: ${exemplo}.');
        
        return function() {
            console.log('2 - O valor da variável exemplo é: ${exemplo}.');
            
            return function() {
                console.log('3 - O valor da variável exemplo é: ${exemplo}.');
            }
        }
    }
}

const initFn1 = init();

const initFn2 = initFn1();

const initFn3 = initFn2();

initFn3();
````

<span style="color: #D00; font-weight: bold">*Isto não é uma boa prática!</span>

***

- **Currying -** É a tecninca de transformarmos uma função com _n_ parâmetros em apenas uma função que recebe 1 parâmetro, e para cada parâmetro vamos retornando uma nova função.

Exemplos:

````javascript
function soma(a, b) {
    return a + b;
}

console.log(soma(2, 2));
console.log(soma(2, 3));
console.log(soma(2, 4));
console.log(soma(2, 5));
````

No exemplo acima vemos que tem um dado que sempre se repete. 

No exemplo abaixo vemos como utilizar o Currying para manter esse dado como uma constante.

````javascript
function soma(a) {
    return function(b) {
        return a + b;
    }
}

const soma2 = soma(2);

console.log(soma2(2));
console.log(soma2(3));
console.log(soma2(4));
console.log(soma2(5));
````

***

- **Hoisting -** Hoisting signifca levantar/suspender algo. 

  É um comportamento que ocorre no JavaScript em declarações de variáveis e funções, que são elevadas ao escopo em que ela se encontra, seja de bloco, função ou global.

  **Hoisting de variável -** Só eleva a criação da variável e não sua atribuição.

  **Hoisting de função -** É içada ao topo como um todo.

Exemplo de Hoisting de Variável:

````javascript
function fn() {
    console.log(text); //Mostrando o conteúdo da variável antes dela ser declarada. Não gera erro, porem o resultado é Undefined.
    
    var text = 'Exemplo';
    
    console.log(text);
}

fn();

/*Seria o mesmo resultado que isso:

function fn() {
	var text;
	console.log(text);
	
	var text = 'Exemplo';
	
	console.log(text);
}

*/
````

***

Exemplo de Hoisting de Função:

````javascript
function fn() {
    log('Hoisting de função');
    
    function log(value) {
        console.log(value);
    } //Na execução, esse bloco inteiro de função será içada para o topo da função fn.
}

fn();

/*Seria o mesmo resultado que isso:

function fn() {
	function log(value) {
		console.log(value);
	}
	
	log('Hoisting de função');
}

*/
````

***

- **Imutabilidade -** Um conceito de linguagem funcional que o JavaScript tem. Em linguagens funcionais, os dados que vamos criando nunca mudam, a variável nunca vai mudar, se você precisa alterar ela, você vai criar uma nova.

Exemplos de Imutabilidade:

````javascript
const user = {
    name: 'Pablo Lucas',
    lastName: 'Santos Marinho'
};

function getUserWithFullName(user) {
    return {
        ...user, //Spread Operator - Para cada propriedade que eu receber do user, ele vai colocar dentro do novo objeto
        fullName: '${user.name} ${user.lastName}'
    }
}

const userWithFullName = getUserWithFullName(user);

console.log(userWithFullName);
````

***

````javascript
const students = [
    {
        name: 'Grace',
        grade: 7
    },
    {
        name: 'Jennifer',
        grade: 4
    },
    {
        name: 'Paul',
        grade: 10
    }
];

function getApprovedStudents(studentsList) {
    return studentsList.filter(student => student.grade >= 7);
}

console.log('Alunos aprovados:');
console.log(getApprovedStudents(students));

console.log('\nLista de alunos:');
console.log(students);
````

***

# Variáveis

Variáveis:

- **var -** O **var** declara uma variável, opcionalmente é possível atribuir à ela um valor em sua inicialização.

  Declarações de variáveis, onde quer que elas ocorram, são processadas antes que qualquer outro código seja executado. O escopo de uma variável declarada com var é seu contexto atual em execução, o qual é a função a qual pertence ou, para variáveis declaradas fora de qualquer função, o escopo é o global.

- **let -** Declara uma variável local no escopo do bloco atual, opcionalmente iniciando-a com um valor.

  let permite que você declare variáveis limitando seu escopo no bloco, instrução, ou em uma expressão na qual ela é usada. Isso é inverso da keyword `var`, que define uma variável globalmente ou no escopo inteiro de uma função, independentemente do escopo de bloco.

- **const -** Constantes possuem escopo de bloco. O valor de uma constante não pode ser alterado por uma atribuição, e ela não pode ser redeclarada.

  A declaração const cria uma variável cujo o valor é fixo, ou seja, uma constante somente leitura. Isso não significa que o valor é imutável, apenas que a variável constante não pode ser alterada ou retribuída.

Escopos:

````javascript
//escopo global

{
    //escopo de bloco
}

function teste() {
    //escopo de função
}
````

***

Exemplo var:

````javascript
var test = 'example';

(() => {
    console.log('Valor dentro da função "${test}"');
    
    if (true) {
        var test = 'Example';
        console.log('Valor dentro do if "${test}"');
    }
    
    console.log('Valor após a execução do if "${test}"');
})();
````

***

Exemplo let:

````javascript
(() => {
    let test = 'valor função';
    console.log('Valor dentro da função "${test}"');
    
    if (true) {
        let test = 'valor if'; //Esse let só existe dentro desse bloco if
        console.log('Valor dentro do if "${test}"');
    }
    
    console.log('Valor após a execução do if "${test}"');
})();
````

<span style="font-weight: bold; color: #D00">*const possui o mesmo resultado</span>

***

Exemplos const:

````javascript
const name = 'Pablo';

/* A variável sendo um tipo primitivo, como uma string
Não podemos alterar o valor */
name = 'Pablo';

// Mas se for um objeto, podemos trocar suas propriedades

const user = {
    name: 'Pablo'
};

user.name = 'Lucas';

// Não podemos fazer o objeto "apontar" para outro lugar
user = {
    name: 'Pablo'
};

const persons = ['Guilherme', 'Pablo', 'Jennifer'];

// Podemos adcionar novos itens
persons.push('João');

// Podemos remover algum item
persons.shift();

// Podemos alterar diretamente
persons[1] = 'James';

console.log('\nArray após as alterações: ', persons);
````

***

# Tipos

- string
- number
- boolean
- null
- undefined
- symbol
- Object
- Function
- Array

## String

Métodos:

````javascript
// Retorna o tamanho de uma string
const textSize = 'Texto'.length;
console.log('Quantidade de caracteres: ${textSize}');

// Retorna um array quebrando a string por um delimitador
const splittedText = 'Texto'.split('x');
console.log('\nArray com as posições separadas pelo delimitador: ', splittedText);

// Busca por um valor e substitui por outro
const replacedText = 'Texto'.replace('Text', 'txeT');
console.log('\nSubstituição de valor: ', replacedText);

// Retorna a "fatia" de um valor
const lastChar = 'Texto'.slice(-1);
console.log('\nÚltima letra de uma string: ', lastChar);


````

