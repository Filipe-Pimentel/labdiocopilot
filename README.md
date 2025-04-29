# labdiocopilot
Lab dio copilot

Card Copilot

Estrutura do Projeto
Pasta do Projeto: IdentificadorBandeiraCartao
Arquivos principais:
index.js (ou main.py, dependendo da linguagem escolhida)
utils.js (ou utils.py) para funções auxiliares
test para testes unitários
Exemplo de Código em JavaScript
Aqui está um exemplo inicial para identificar bandeiras de cartões de crédito:

Arquivo: index.js

const { identificarBandeira } = require('./utils');

// Exemplo de uso
const numeroCartao = '4111111111111111'; // Número fictício
const bandeira = identificarBandeira(numeroCartao);

console.log(`A bandeira do cartão é: ${bandeira}`);

-----

function identificarBandeira(numeroCartao) {
    const regexes = {
        Visa: /^4[0-9]{12}(?:[0-9]{3})?$/,
        MasterCard: /^5[1-5][0-9]{14}$/,
        Amex: /^3[47][0-9]{13}$/,
        Discover: /^6(?:011|5[0-9]{2})[0-9]{12}$/,
        JCB: /^(?:2131|1800|35\d{3})\d{11}$/,
    };

    for (const [bandeira, regex] of Object.entries(regexes)) {
        if (regex.test(numeroCartao)) {
            return bandeira;
        }
    }

    return 'Bandeira desconhecida';
}

module.exports = { identificarBandeira };

----

Testes Unitários: utils.test.js

const { identificarBandeira } = require('../utils');

test('Identifica Visa corretamente', () => {
    expect(identificarBandeira('4111111111111111')).toBe('Visa');
});

test('Identifica MasterCard corretamente', () => {
    expect(identificarBandeira('5105105105105100')).toBe('MasterCard');
});

test('Retorna "Bandeira desconhecida" para números inválidos', () => {
    expect(identificarBandeira('1234567890123456')).toBe('Bandeira desconhecida');
});

------

Aqui se encontra o código da aplicação, no qual fora solicitada e indexada, baseado nas aulas anteriores.

