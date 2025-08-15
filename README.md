const prompt = require('prompt-sync')();

const numeroAleatorio = Math.floor(Math.random() * 100) + 1;
let tentativas = 0;
let adivinhou = false;

console.log("Bem-vindo ao jogo de Adivinhe o Número!");
console.log("Estou pensando em um número entre 1 e 100.");

while (!adivinhou) {

    const palpiteStr = prompt("Seu palpite: ");
    const palpite = parseInt(palpiteStr);

    if (isNaN(palpite)) {
        console.log("Isso não é um número. Tente novamente.");
        continue;
    }

    tentativas++;

    if (palpite < numeroAleatorio) {
        console.log("Muito baixo!");
    } else if (palpite > numeroAleatorio) {
        console.log("Muito alto!");
    } else {
        adivinhou = true;
        console.log(`Parabéns! Você adivinhou o número ${numeroAleatorio} em ${tentativas} tentativas.`);
    }
}
