# Instruções

- Faça uma cópia deste arquivo .md para um repositório próprio
- Resolva as 6 questões objetivas assinalando a alternativa correta
- Resolva as 4 questões dissertativas escrevendo no próprio arquivo .md
  - lembre-se de utilizar as estruturas de código como ``esta aqui com ` `` ou
```javascript
//esta aqui com ```
let a = "olá"
let b = 10
print(a)
```
- Resolva as questões com uso do Visual Studio Code ou ambiente similar.
- Teste seus códigos antes de trazer a resposta para cá.
- Cuidado com ChatGPT e afins: entregar algo só para ganhar nota não faz você aprender e ficar mais inteligente. Não seja dependente da máquina! (E não se envolva em plágio!)
- ao final, publique seu arquivo lista_02.md com as respostas em seu repositório, e envie o link pela Adalove. 

# Questões objetivas

**1)** Considere o seguinte código JavaScript:

```javascript
//EX01
let p = 10;
let q = 3;
let r = 6;

let resultado = (p % q === 1) && (r * 2 > p) || (q + r < p);
console.log(resultado);

const valores = [3, 6, 9, 12, 15];
let produto = 1;

for (let j = 0; j < valores.length; j++) {
  produto *= valores[j];
}

console.log("O produto dos valores é:", produto);


```
Qual das seguintes alternativas melhor descreve o que o código faz?

A) O código avalia a expressão booleana, imprime `true`, calcula o produto dos números na lista e imprime o resultado no console.

B) O código avalia a expressão booleana, imprime `false`, calcula o produto dos números na lista e imprime o resultado no console.

C) O código avalia a expressão booleana, imprime `true` e, em seguida, verifica se o número 6 está na lista.

D) O código avalia a expressão booleana, imprime `false` e ordena os valores em ordem crescente.


**Resposta: A**
______

**2)** O código a seguir contém duas funções que calculam o limite de crédito de um cliente com base nos seus gastos e na renda mensal.

```javascript
// Versão 1 da função de análise de crédito
function analisarCredito1() {
    var compras = [2500, 1200, 800, 100];
    var totalCompras = compras[0];
    var limite = 5000;
    var status = 'aprovado';
    var saldoDisponivel = 0;
    var i = 1;

    do {
        totalCompras += compras[i];
        i++;
    } while (limite >= totalCompras && i < compras.length);

    saldoDisponivel = limite - totalCompras;

    if (saldoDisponivel < 0) {
        status = 'negado';
    }
    console.log(`Seu crédito foi ${status}. Saldo disponível: ${saldoDisponivel}.`);
}
```

```javascript
// Versão 2 da função de análise de crédito
function analisarCredito2() {
    var compras = [2500, 1200, 800, 100];
    var totalCompras = compras[0];
    var limite = 5000;
    var status = 'aprovado';
    var saldoDisponivel = 0;
    var i = 1;

    while (limite >= totalCompras && i < compras.length) {
        totalCompras += compras[i];
        i++;
    }

    saldoDisponivel = limite - totalCompras;

    if (saldoDisponivel < 0) {
        status = 'negado';
    }
    console.log(`Seu crédito foi ${status}. Saldo disponível: ${saldoDisponivel}.`);
}
```
Se ambas as funções forem executadas com os valores fornecidos, qual será a saída exibida no console?

A) Ambas as funções exibirão: 'Seu crédito foi aprovado. Saldo disponível: 400.'

B) analisarCredito1() exibirá: 'Seu crédito foi negado. Saldo disponível: -600.', enquanto analisarCredito2() exibirá: 'Seu crédito foi negado. Saldo disponível: -200.'

C) analisarCredito1() exibirá: 'Seu crédito foi negado. Saldo disponível: -200.', enquanto analisarCredito2() exibirá: 'Seu crédito foi aprovado. Saldo disponível: 100.'

D) Ambas as funções exibirão: 'Seu crédito foi aprovado Saldo disponível: 500.'

**Resposta: A**
______

**3)** Considere o seguinte trecho de código em JavaScript:
```javascript
//EX03
const idade = 21;

if (idade >= 18 && idade < 60) {
  console.log("Você é um adulto!");
} else if (idade < 18) {
  console.log("Você é menor de idade!");
} else {
  console.log("Você está na melhor idade!");
}
```
Qual das seguintes alternativas melhor descreve o comportamento do código?

A) O código verifica se a idade indica um adulto ou um idoso e exibe a mensagem correspondente.

B) O código verifica se a idade pertence à faixa adulta. Se for, exibe "Você é um adulto!". Caso contrário, verifica se é menor de idade e exibe "Você é menor de idade!". Se nenhuma das condições anteriores for verdadeira, exibe "Você está na melhor idade!".

C) O código verifica se a idade está entre 18 e 60 anos e, se for, imprime "Você é um adulto!". Se não estiver nesse intervalo, imprime "Você está na melhor idade!".

D) O código verifica se a idade é menor de 18, entre 18 e 60 ou acima de 60, imprimindo uma mensagem específica para cada caso.

**Resposta: B**
______

**4)** Qual será o resultado impresso no console após a execução do seguinte código?
```javascript
//EX04
var energiaDisponivel = 1200;
var bateriaExtra = 400;
var consumoDispositivos = [300, 600, 500, 200, 400];

for (var i = 0; i < consumoDispositivos.length; i++) {
    var consumo = consumoDispositivos[i];

    if (consumo <= energiaDisponivel) {
        console.log("Dispositivo " + (i+1) + " ligado. Energia restante: " + (energiaDisponivel - consumo));
        energiaDisponivel -= consumo;
    } else if (consumo <= energiaDisponivel + bateriaExtra) {
        console.log("Dispositivo " + (i+1) + " ligado com bateria extra. Energia restante: " + ((energiaDisponivel + bateriaExtra) - consumo));
        energiaDisponivel = 0;
        bateriaExtra -= (consumo - energiaDisponivel);
    } else {
        console.log("Dispositivo " + (i+1) + " não pode ser ligado. Energia insuficiente.");
    }
}
```

Escolha a opção que responde corretamente:

A)
Dispositivo 1 ligado. Energia restante: 900

Dispositivo 2 ligado com bateria extra. Energia restante: 700

Dispositivo 3 ligado. Energia restante: 200

Dispositivo 4 ligado com bateria extra. Energia restante: 0

Dispositivo 5 ligado. Energia restante: -200

B)
Dispositivo 1 ligado. Energia restante: 900

Dispositivo 2 ligado com bateria extra. Energia restante: 700

Dispositivo 3 ligado. Energia restante: 200

Dispositivo 4 não pode ser ligado. Energia insuficiente.

Dispositivo 5 não pode ser ligado. Energia insuficiente.

C)
Dispositivo 1 ligado. Energia restante: 900

Dispositivo 2 ligado com bateria extra. Energia restante: 700

Dispositivo 3 ligado. Energia restante: 400

Dispositivo 4 não pode ser ligado. Energia insuficiente.

D)
Dispositivo 1 ligado. Energia restante: 900

Dispositivo 2 ligado. Energia restante: 300

Dispositivo 3 ligado com bateria extra. Energia restante: 200

Dispositivo 4 não pode ser ligado. Energia insuficiente.

Dispositivo 5 não pode ser ligado. Energia insuficiente.

**Resposta: D**
______

**5)** Qual é a principal função do método update() em um jogo desenvolvido com Phaser.js?

Escolha a opção que melhor descreve seu propósito:

A) O método update() é responsável por carregar os assets do jogo antes da cena ser exibida.

B) O método update() é chamado continuamente a cada quadro (frame) do jogo, sendo usado para atualizar a lógica, movimentação e interações dos objetos na cena.

C) O método update() renderiza todos os sprites na tela e garante que a física do jogo seja processada corretamente.

D) O método update() é chamado apenas uma vez após a criação da cena, sendo utilizado para configurar variáveis iniciais do jogo.

**Resposta: B**
______

**6)** Qual é o principal objetivo do módulo Matter.js Physics em Phaser.js?

Escolha a opção que responde corretamente:

A) Simular física avançada, incluindo corpos rígidos, colisões complexas e interação entre objetos com gravidade e forças.

B) Gerenciar eventos de entrada do usuário, como cliques e toques na tela, permitindo movimentação de personagens.

C) Renderizar gráficos otimizados para jogos 2D e garantir uma taxa de quadros estável.

D) Criar animações automáticas para sprites e objetos interativos sem necessidade de programação de movimentação.

**Resposta: A**
______

# Questões dissertativas

**7)** Uma loja online deseja implementar um sistema de classificação de pedidos com base no valor total da compra. O sistema deve determinar a categoria de um pedido com as seguintes regras:

```
Pedidos abaixo de R$50,00 → "Frete não disponível!"

Pedidos entre R$50,00 e R$199,99 (inclusive) → "Frete com custo adicional!"

Pedidos de R$200,00 ou mais → "Frete grátis!"
```
Implemente um pseudocódigo que receba o valor total da compra e exiba a classificação correta do frete para o cliente.

```
Algoritmo ClassificarFrete
  // Recebe o valor total da compra e retorna a classificação do frete
  Função ClassificarFrete(valorTotal)
    // Verifica se o pedido é menor que R$50,00
    Se valorTotal < 50.00 Então
      Escrever("Frete não disponível!")
    
    // Verifica se o pedido está entre R$50,00 e R$199,99
    Senão Se valorTotal >= 50.00 E valorTotal <= 199.99 Então
      Escrever("Frete com custo adicional!")
    
    // Pedidos de R$200,00 ou mais
    Senão
      Escrever("Frete grátis!")
    FimSe
  FimFunção
  
  // Exemplo de uso
  valorPedido <- LerValorDoUsuario()
  ClassificarFrete(valorPedido)
FimAlgoritmo
```
______

**8)** Considere a implementação da classe base Veiculo em um sistema de modelagem de veículos. Sua tarefa é implementar, utilizando pseudocódigo, as classes derivadas Carro e Moto, que herdam da classe Veiculo, adicionando atributos específicos e métodos para calcular o consumo de combustível de um carro e de uma moto, respectivamente.

```
Classe Veiculo:
Atributos:

modelo
ano
Método Construtor(modelo, ano):

Define os valores dos atributos modelo e ano com os valores passados como parâmetro.
Método CalcularConsumo():
```
Implementação genérica para cálculo de consumo, a ser sobrescrita pelas subclasses.
Agora, implemente as classes Carro e Moto, garantindo que ambas herdem de Veiculo e possuam métodos específicos para calcular o consumo de combustível com base na quilometragem e eficiência do veículo.

```
// Classe Veiculo (já definida)
Classe Veiculo
  Atributos:
    modelo
    ano
  
  Construtor(modelo, ano)
    this.modelo = modelo
    this.ano = ano
  
  CalcularConsumo()
    // Implementação genérica a ser sobrescrita
    Retornar "Método a ser implementado pelas subclasses"
FimClasse

// Classe Carro (herda de Veiculo)
Classe Carro herda Veiculo
  Atributos:
    potenciaMotor // em cavalos
    numeroPortas
    capacidadeTanque // em litros
  
  Construtor(modelo, ano, potenciaMotor, numeroPortas, capacidadeTanque)
    // Chama o construtor da classe pai
    Super(modelo, ano)
    
    // Inicializa os atributos específicos de Carro
    this.potenciaMotor = potenciaMotor
    this.numeroPortas = numeroPortas
    this.capacidadeTanque = capacidadeTanque
  
  CalcularConsumo(quilometragem, litrosConsumidos)
    // Calcula o consumo em km/l
    consumoMedio = quilometragem / litrosConsumidos
    
    // Aplica fator de ajuste baseado na potência do motor
    fatorPotencia = 1 - (this.potenciaMotor / 300) // Quanto maior a potência, menor a eficiência
    consumoAjustado = consumoMedio * fatorPotencia
    
    Retornar "O carro " + this.modelo + " tem um consumo médio de " + consumoAjustado.toFixed(2) + " km/l"
FimClasse

// Classe Moto (herda de Veiculo)
Classe Moto herda Veiculo
  Atributos:
    cilindradas
    tipoMotor // ex: "2 tempos", "4 tempos"
    capacidadeTanque // em litros
  
  Construtor(modelo, ano, cilindradas, tipoMotor, capacidadeTanque)
    // Chama o construtor da classe pai
    Super(modelo, ano)
    
    // Inicializa os atributos específicos de Moto
    this.cilindradas = cilindradas
    this.tipoMotor = tipoMotor
    this.capacidadeTanque = capacidadeTanque
  
  CalcularConsumo(quilometragem, litrosConsumidos)
    // Calcula o consumo em km/l
    consumoMedio = quilometragem / litrosConsumidos
    
    // Aplica fator de ajuste baseado nas cilindradas
    fatorCilindradas = 1 - (this.cilindradas / 2000) // Quanto maior a cilindrada, menor a eficiência
    
    // Ajuste adicional pelo tipo de motor
    fatorTipoMotor = (this.tipoMotor === "4 tempos") ? 1.2 : 0.9 // 4 tempos é mais eficiente
    
    consumoAjustado = consumoMedio * fatorCilindradas * fatorTipoMotor
    
    Retornar "A moto " + this.modelo + " tem um consumo médio de " + consumoAjustado.toFixed(2) + " km/l"
FimClasse
```
______

**9)** Você é um cientista da NASA e está ajudando no desenvolvimento de um sistema de pouso para sondas espaciais em Marte. Seu objetivo é calcular o tempo necessário para que a sonda reduza sua velocidade até um nível seguro para pouso, considerando uma velocidade inicial de entrada na atmosfera marciana e uma taxa de desaceleração constante causada pelo atrito atmosférico e retrofoguetes.

Entretanto, a sonda não pode ultrapassar um tempo máximo de descida para evitar desvios orbitais, nem pode desacelerar além de um limite mínimo, pois isso poderia causar instabilidade no pouso.

Implemente a lógica dessa simulação em pseudocódigo, considerando a seguinte equação para atualização da velocidade:

Considere a fórumla de atualização velocidade:
```
    velocidade = velocidadeInicial - desaceleracao * tempo
```
Seu programa deve determinar quanto tempo será necessário para que a sonda atinja uma velocidade segura de pouso, sem ultrapassar os limites estabelecidos.

```
Algoritmo SimulacaoPousoMarte
  // Parâmetros de entrada
  velocidadeInicial <- 1000 // m/s (exemplo)
  desaceleracao <- 20     // m/s² (exemplo)
  velocidadeSegura <- 10  // m/s (velocidade segura para pouso)
  tempoMaximo <- 120      // s (tempo máximo de descida permitido)
  desaceleracaoMinima <- 5 // m/s² (limite mínimo de desaceleração)
  
  // Validar se a desaceleração está dentro dos limites permitidos
  Se desaceleracao < desaceleracaoMinima Então
    Escrever("ALERTA: Desaceleração muito baixa. Risco de instabilidade no pouso!")
    Retornar
  FimSe
  
  // Calcular tempo necessário para atingir velocidade segura
  tempoNecessario <- (velocidadeInicial - velocidadeSegura) / desaceleracao
  
  // Verificar se o tempo necessário excede o limite máximo
  Se tempoNecessario > tempoMaximo Então
    Escrever("ALERTA: Tempo de descida excede o limite máximo! Desvio orbital iminente.")
    Escrever("Tempo necessário: ", tempoNecessario, " segundos")
    Escrever("Tempo máximo permitido: ", tempoMaximo, " segundos")
    
    // Calcular a desaceleração mínima necessária para pousar dentro do limite de tempo
    desaceleracaoNecessaria <- (velocidadeInicial - velocidadeSegura) / tempoMaximo
    Escrever("Desaceleração necessária: ", desaceleracaoNecessaria, " m/s²")
    
    Se desaceleracaoNecessaria > 3 * desaceleracaoMinima Então
      Escrever("ALERTA CRÍTICO: Desaceleração necessária é muito alta para um pouso seguro!")
      Escrever("Recomendação: Abortar missão ou ajustar trajetória de entrada.")
    Senão
      Escrever("Recomendação: Aumentar potência dos retrofoguetes para atingir a desaceleração necessária.")
    FimSe
    
    Retornar
  FimSe
  
  // Simulação de descida
  tempo <- 0
  velocidadeAtual <- velocidadeInicial
  
  Enquanto velocidadeAtual > velocidadeSegura
    // Atualizar velocidade conforme a fórmula
    velocidadeAtual <- velocidadeInicial - desaceleracao * tempo
    
    // Incrementar tempo
    tempo <- tempo + 1
    
    // Verificar se ainda estamos dentro do limite de tempo
    Se tempo > tempoMaximo Então
      Escrever("ALERTA: Limite de tempo excedido durante a descida! Abortando simulação.")
      Retornar
    FimSe
  FimEnquanto
  
  // Resultados da simulação
  Escrever("=============== RESULTADO DA SIMULAÇÃO ===============")
  Escrever("Pouso seguro alcançado!")
  Escrever("Tempo total de descida: ", tempo, " segundos")
  Escrever("Velocidade final: ", velocidadeAtual, " m/s")
FimAlgoritmo
```
______

**10)** Em um sistema de análise financeira, as operações de investimento de uma empresa podem ser representadas por matrizes, onde cada linha representa um tipo de investimento e cada coluna representa um período de tempo.

A seguir, é fornecida a implementação da função SomarMatrizesInvestimento(matrizA, matrizB), que soma os valores de duas matrizes de investimento. Sua tarefa é implementar uma função semelhante, porém que realize a multiplicação das matrizes de investimento, determinando como os investimentos afetam os resultados ao longo do tempo.

```
Função SomarMatrizesInvestimento(matrizA, matrizB):  
    # Verifica se as matrizes têm o mesmo número de linhas e colunas  
    Se tamanho(matrizA) ≠ tamanho(matrizB) então:  
        Retornar "As matrizes não podem ser somadas. Elas têm dimensões diferentes."  
    Senão:  
        linhas <- tamanho(matrizA)  
        colunas <- tamanho(matrizA[0])  
        matrizResultado <- novaMatriz(linhas, colunas)  

        # Loop para percorrer cada elemento das matrizes e calcular a soma  
        Para i de 0 até linhas-1 faça:  
            Para j de 0 até colunas-1 faça:  
                matrizResultado[i][j] <- matrizA[i][j] + matrizB[i][j]  

        Retornar matrizResultado  

# Exemplo de uso da função  
investimentosAno1 <- [[1000, 2000], [1500, 2500]]  
investimentosAno2 <- [[1200, 1800], [1300, 2700]]  

totalInvestimentos <- SomarMatrizesInvestimento(investimentosAno1, investimentosAno2)  
Escrever("Total de investimentos acumulados:")  
ImprimirMatriz(totalInvestimentos)  
```
Agora, implemente a função MultiplicarMatrizesInvestimento(matrizA, matrizB), que multiplica as duas matrizes, simulando o efeito de diferentes fatores de crescimento e impacto financeiro nos investimentos ao longo do tempo.

```
Função MultiplicarMatrizesInvestimento(matrizA, matrizB):
    # Verificar se o número de colunas da primeira matriz é igual 
    # ao número de linhas da segunda matriz (requisito para multiplicação)
    Se tamanho(matrizA[0]) ≠ tamanho(matrizB) então:
        Retornar "As matrizes não podem ser multiplicadas. O número de colunas da primeira matriz deve ser igual ao número de linhas da segunda matriz."
    Senão:
        linhasA <- tamanho(matrizA)
        colunasA <- tamanho(matrizA[0])
        colunasB <- tamanho(matrizB[0])
        
        # Criar matriz de resultado
        matrizResultado <- novaMatriz(linhasA, colunasB)
        
        # Preencher a matriz de resultado
        Para i de 0 até linhasA-1 faça:
            Para j de 0 até colunasB-1 faça:
                matrizResultado[i][j] <- 0
                
                # Calcular o valor da posição atual
                Para k de 0 até colunasA-1 faça:
                    matrizResultado[i][j] <- matrizResultado[i][j] + (matrizA[i][k] * matrizB[k][j])
        
        Retornar matrizResultado

# Exemplo de uso da função
investimentos <- [[1000, 2000], [1500, 2500]]
fatoresImpacto <- [[1.2, 0.8], [0.9, 1.3]]

resultadoInvestimentos <- MultiplicarMatrizesInvestimento(investimentos, fatoresImpacto)
Escrever("Resultado dos investimentos após aplicação dos fatores de impacto:")
ImprimirMatriz(resultadoInvestimentos)
```