# Resolução dos desafios de programação

Os códigos usados para a resolução dos desafios são em HTML e JavaScript. No entanto, em algumas questões é utilizado somente JavaScript.

#### Desafios - Respostas

1) Imagine que você está criando um sistema escolar para obter a média dos alunos da sala. Foram realizadas 3 avaliações com nota máxima de 10 pontos. Aline, tirou na primeira nota o total de 8 pontos, na segunda nota tirou 9 pontos e na terceira nota 7 pontos. 

Escreva um programa que receba as notas, faça o cálculo da média e imprima o resultado final da média.

```js & html
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculo de Média</title>
</head>
<body>
    <div id="main">

        <h1>Calculo de Média</h1>
        <input type="number" max="10" id="primeira_nota"
        placeholder="Insrira a primeira nota">

        <input type="number" max="10" id="segunda_nota"
        placeholder="Insrira a segunda nota">

        <input type="number" max="10" id="terceira_nota"
        placeholder="Insrira a terceira nota">

        <button id="calcular" onclick="calcular()">Calcular</button>

        <p>A sua média é: <span id="media"></span></p>
        <p id="status"></p>

    </dive>

    <script> 

        function calcular(){

            var n1, n2, n3, media;

            n1 = document.getElementById('primeira_nota').value;
            n2 = document.getElementById('segunda_nota').value;
            n3 = document.getElementById('terceira_nota').value;

            media = (parseFloat(n1) + parseFloat(n2) +
            parseFloat (n3)) / 3

            document.getElementById('media').innerHTML = media

            if(media <7){
                document.getElementById('status').innerHTML = 
                "Reprovado"

            } else{
                document.getElementById('status').innerHTML = 
                "Aprovado"

            }


        }


    </script>
</body>
</html>
```

2)  Tais está participando de um sorteio na Loteria e recebeu uma lista de números aleatórios para poder apostar. Os números foram: 15, 8, 90, 75, 102, 6 e 2. Por ser bastante cautelosa, ela gostaria de saber qual é o menor número e qual é o maior número. 

Ajude Tais e escreva um programa que faça a lógica de programação para organização dos números, receba os números da lista e imprima na tela o menor número digitado e o maior número digitado.

```js
var n1 = 15;
var n2 = 8;
var n3 = 90;
var n4 = 75;
var n5 = 102;
var n6 = 6;
var n7 = 2;

var max = Math.max(n1, n2, n3, n4, n5, n6, n7);
var min = Math.min(n1, n2, n3, n4, n5, n6, n7);

var pre = document.body.appendChild(document.createElement('pre'));
pre.textContent = 'dos valores ' + n1 + ', ' + n2 + ', ' + n3 + ',' + n4 + ', ' + n5 + ', ' + n6 + ' e ' + n7 + ', ';
pre.textContent += ' o máximo é ' + max + ' e o mínimo é ' + min;
```

3) Escreva um programa que faça a ordenação dos frascos: 12, 5, 23, 17, 8, 14, 3, 19.

```js
let numeros = [12, 5, 23, 17, 8, 14, 3, 19,];
numeros.sort(function (a, b){
  return a - b;
});
console.log(numeros);
```

4) Em uma pequena vila, o fazendeiro precisa separar os números primos para determinar quantos novos campos plantar. Ele pede sua ajuda para identificar esses números criando um algoritmos. Os números são: 23, 16, 11, 8, 19, 14, 5, 21.

```js
function primeiroNumero(num) {
    for (var divisor = 2; divisor < num; divisor++) 
    if (num % divisor == 0) return false;
    return true;
}

var determinadoNumero = 25;

for (var i = 2; i < determinadoNumero; i++) if (primeiroNumero(i)) console.log(i);
```

5) Escreva um programa que conte o número de palavras em uma frase fornecida pelo usuário. A frase é: "What is Lorem Ipsum?" 

```js

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Contador</title>
</head>
<body>
    <h1>Contador de Caracteres</h1>

    <form name="form_main">
        <fieldset>
            <legend>Contador</legend>
            <label for="text">Texto:</label> <br>
            <textarea name="text" id="text" cols="30" rows="10" oninput="countText()"></textarea><br>
            <label for="characters">Caracteres: </label><span id="characters" ></span><br>
            <label for="words">Palavras: </label><span id="words" ></span><br>
            <label for="rows">Linhas: </label><span id="rows" ></span><br>
        </fieldset>
    </form>

    <script>
        function countText(){
            let text = document.form_main.text.value;

            console.log(text);

            document.getElementById('characters').innerText = text.length;
            document.getElementById('words').innerText = text.length;
            document.getElementById('rows').innerText = text.split(/\n/).length;
        }
    </script>
</body>
</html>
```

6) Escreva um programa para encontrar o fatorial do número 12.

```js
function numeroFatorial(n){
  let fatorial = n
  if(n==0){
    fatorial = 1
  }

  while(n> 1){
    n--
    fatorial = fatorial * n
  }


  return fatorial

}

const n = numeroFatorial(12)

console.log (n)
```

7) Em uma loja de conveniência, um cliente comprou três itens e precisa calcular o total da compra. Os preços dos itens são R$ 2,50, R$ 3,75 e R$ 1,99. Crie um algoritmo que retorne o valor total.

```js 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <input type="number" id="n1" />
    <input type="number" id="n2" />
    <input type="number" id="n3" />

    <button onClick="calcular()">Calcular</button>

    <script>
        function calcular(){
            var n1 = document.getElementById("n1").value
            var n2 = document.getElementById("n2").value
            var n3 = document.getElementById("n3").value

            var media = (Number(n1) + Number(n2) + Number(n3))

            alert(`A soma ds valores é: ${media}`)

            console.log(`A soma ds valores é: ${media}`)
        }
    </script>

</body>
</html>
```

8) Em um sistema de biblioteca, é necessário calcular a multa a ser paga por um usuário que atrasou a devolução de um livro. A multa é de R$ 0,50 por dia de atraso. O usuário atrasou a devolução do livro em 7 dias. Crie um algoritmo que faça o cálculo total que o aluno deverá pagar a biblioteca.

```js
const valorMultaPorDia = 0.50;

const diasAtraso = 7;

const totalMulta = valorMultaPorDia * diasAtraso;

console.log("O total da multa a ser pago é: R$" + totalMulta.toFixed(2));
```

9) Em um jogo de RPG, o personagem do jogador possui pontos de vida (HP) que são reduzidos quando ele sofre danos dos inimigos. Seu personagem começa com 100 pontos de vida e sofre danos de 20 pontos em um ataque. Crie um algoritmo informando quantos pontos de vida restarão após três ataques?

```js
let pontosDeVida = 100;
const danoPorAtaque = 20;

for (let i = 0; i < 3; i++) {
    pontosDeVida -= danoPorAtaque;
}

console.log("Pontos de vida restantes após três ataques:", pontosDeVida);
```

10) Desenvolver um programa para contar o número de letras maiúsculas da string abaixo: “LoReM IpSuM Is sImPlY DuMmY TeXt oF ThE PrInTiNg aNd tYpEsEtTiNg iNdUsTrY”

```js
function contarLetrasMaiusculas(string) {
    let count = 0;
    for (let i = 0; i < string.length; i++) {
        if (string[i] >= 'A' && string[i] <= 'Z') {
            count++;
        }
    }
    return count;
}

//Exemplo
let minhaString = "LoReM IpSuM Is sImPlY DuMmY TeXt oF ThE PrInTiNg aNd tYpEsEtTiNg iNdUsTrY";
let numeroDeMaiusculas = contarLetrasMaiusculas(minhaString);
console.log("Número de letras maiúsculas na string:", numeroDeMaiusculas);
```
11) Crie uma lógica para calcular a idade de uma pessoa. Essa lógica deverá receber um valor de ano de nascimento no formato “yyyy-MM-dd” e deverá retornar o número da idade da pessoa como resultado.

```js
function calcularIdade(dataNascimento) {
    
    var partesData = dataNascimento.split("-");
    var anoNascimento = parseInt(partesData[0]);
    var mesNascimento = parseInt(partesData[1]);
    var diaNascimento = parseInt(partesData[2]);
    
    var dataAtual = new Date();
    var anoAtual = dataAtual.getFullYear();
    var mesAtual = dataAtual.getMonth() + 1; 
    var diaAtual = dataAtual.getDate();
    
    var idade = anoAtual - anoNascimento;
    
    if (mesAtual < mesNascimento || (mesAtual === mesNascimento && diaAtual < diaNascimento)) {
        idade--;
    }
    
    return idade;
}

// Exemplo 
var dataNascimento = "1999-08-01"; 
var idade = calcularIdade(dataNascimento);
console.log("A idade é: " + idade);

```
