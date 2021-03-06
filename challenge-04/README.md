# Desafio da semana #4

```js
/*
Declare uma variável chamada `isTruthy`, e atribua a ela uma função que recebe
um único parâmetro como argumento. Essa função deve retornar `true` se o
equivalente booleano para o valor passado no argumento for `true`, ou `false`
para o contrário.
*/
var isTruthy = function(teste) {
	if(teste) {
		teste = true
	} else {
		teste = false
	}
	return teste
}

//Outra solução:
var isTruthy = function(teste) {
	return teste ? true : false
}

//Outra solução:
var isTruthy = function(teste) {
	return !!teste
}

// Invoque a função criada acima, passando todos os tipos de valores `falsy`.
isTruthy(0) //NaN, false, -0, '', ""

/*
Invoque a função criada acima passando como parâmetro 10 valores `truthy`.
*/
isTruthy(32)

/*
Declare uma variável chamada `carro`, atribuindo à ela um objeto com as
seguintes propriedades (os valores devem ser do tipo mostrado abaixo):
- `marca` - String
- `modelo` - String
- `placa` - String
- `ano` - Number
- `cor` - String
- `quantasPortas` - Number
- `assentos` - Number - cinco por padrão
- `quantidadePessoas` - Number - zero por padrão
*/
var carro = {
	marca: 'Audi',
	modelo: 'A3',
	placa: 'ABC-1234',
	ano: 2015,
	cor: 'Branco',
	quantasPortas: 2,
	assentos: 5,
	quantidadedePessoas: 0
}

/*
Crie um método chamado `mudarCor` que mude a cor do carro conforme a cor
passado por parâmetro.
*/
carro.mudarCor = function(novaCor) {
	carro.cor = novaCor
}

/*
Crie um método chamado `obterCor`, que retorne a cor do carro.
*/
carro.obterCor = function() {
	return carro.cor
}

/*
Crie um método chamado `obterModelo` que retorne o modelo do carro.
*/
carro.obterModelo = function() {
	return carro.modelo
}

/*
Crie um método chamado `obterMarca` que retorne a marca do carro.
*/
carro.obterMarca = function() {
	return carro.marca
}

/*
Crie um método chamado `obterMarcaModelo`, que retorne:
"Esse carro é um [MARCA] [MODELO]"
Para retornar os valores de marca e modelo, utilize os métodos criados.
*/
carro.obterMarcaModelo = function() {
	return "Esse carro é um " + carro.obterMarca() + ' ' + carro.obterModelo()
}

/*
Crie um método que irá adicionar pessoas no carro. Esse método terá as
seguintes características:
- Ele deverá receber por parâmetro o número de pessoas entrarão no carro. Esse
número não precisa encher o carro, você poderá acrescentar as pessoas aos
poucos.
- O método deve retornar a frase: "Já temos [X] pessoas no carro!"
- Se o carro já estiver cheio, com todos os assentos já preenchidos, o método
deve retornar a frase: "O carro já está lotado!"
- Se ainda houverem lugares no carro, mas a quantidade de pessoas passadas por
parâmetro for ultrapassar o limite de assentos do carro, então você deve
mostrar quantos assentos ainda podem ser ocupados, com a frase:
"Só cabem mais [QUANTIDADE_DE_PESSOAS_QUE_CABEM] pessoas!"
- Se couber somente mais uma pessoa, mostrar a palavra "pessoa" no retorno
citado acima, no lugar de "pessoas".
*/
carro.adicionarPessoas = function(quantidadeEntrando) {
	if(quantidadeEntrando > 0) {
		if(carro.assentos - carro.quantidadedePessoas <= 0) {
			return "O carro já está lotado!"
		} else if(quantidadeEntrando > (carro.assentos - carro.quantidadedePessoas)) {
			if((carro.assentos - carro.quantidadedePessoas) === 1) {
				return "Só cabe mais 1 pessoa!"
			} else {
				return "Só cabem mais " + (carro.assentos - carro.quantidadedePessoas) + " pessoas!"
			}
		} else {
			carro.quantidadedePessoas += quantidadeEntrando
			return "Já temos " + carro.quantidadedePessoas + " no carro!"
		}
	} else if((quantidadeEntrando + carro.quantidadedePessoas) < 0) {
		return "Você só pode tirar " + carro.quantidadedePessoas + " do carro!"
	} else {
		carro.quantidadedePessoas += quantidadeEntrando
			return "Agora temos " + carro.quantidadedePessoas + " no carro!"
	}
}

/*
Agora vamos verificar algumas informações do carro. Para as respostas abaixo,
utilize sempre o formato de invocação do método (ou chamada da propriedade),
adicionando comentários _inline_ ao lado com o valor retornado, se o método
retornar algum valor.

Qual a cor atual do carro?
*/
?

// Mude a cor do carro para vermelho.
?

// E agora, qual a cor do carro?
?

// Mude a cor do carro para verde musgo.
?

// E agora, qual a cor do carro?
?

// Qual a marca e modelo do carro?
?

// Adicione 2 pessoas no carro.
?

// Adicione mais 4 pessoas no carro.
?

// Faça o carro encher.
?

// Tire 4 pessoas do carro.
?

// Adicione 10 pessoas no carro.
?

// Quantas pessoas temos no carro?
?
