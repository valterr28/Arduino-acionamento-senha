# PROJETO LGP ARDUINO


João Gabriel Grah Machado

---
Valter Rogério da Silva Júnior

---
622

---
Lógica da programação - Carlos Speranza



## Links

[Github](https://github.com/valterr28/Arduino-acionamento-senha)
[Fluxograma](https://)
[Código](https://drive.google.com/file/d/1keEei7JQ_Fq-lYnQXb5YXb-tzqS21Ci-/view?usp=sharing)
[Guia de Conexões](https://drive.google.com/file/d/18Dcz624WUKtDAnQRxaulzMFy0aoJImCS/view?usp=sharing)
[Relatório escrito do projeto](https://drive.google.com/file/d/17sE5uPrXecWP6FvEGLbqAQpM0q4Be4Yi/view?usp=sharing)
[Vídeo - Drive](https://)

## Introdução

O sistema desenvolvido se utiliza da plataforma Arduino para facilitar suas funções,
no caso o sistema é usado para acionamento de circuito por meio de uma senha, usaremos o
exemplo de acionar uma fechadura eletrônica, porém pode ser utilizado para muitos outros
meios, como ligar tomadas ou até mesmo ligar sistemas inteiros, porém com necessidade de
adaptação para tensões mais altas.


## Descrição de Hardware

Para este projeto é utilizado componentes simples, pode ser utilizado qualquer módulo
de Arduíno que contenha no mínimo 12 portas digitais, para testes do projeto foi utilizado o
Arduíno Uno. Um microcontrolador Arduino é composto por série de sensores e permite
integração direta com outros dispositivos, sendo possível criações variadas, das simples até as
mais robustas.

Tendo dois Leds para noção de funcionamento, necessitam de resistor de 1K
Um buzzer, dispositivo de sinalização por áudio, para noção de funcionamento do
sistema e para alerta de erro.
Um teclado matricial 4x4, linhas e colunas formando uma matriz, quando pressionado
conecta a linha com a coluna com a qual está ligado.
Um módulo relé, funciona como um interruptor, ideal para circuitos que exijam até
10A contínuos utilizando microcontroladores, para testes foi baseado um com suporte a 12V
que é o normal utilizado para fechaduras eletrônicas simples.
Uma Protoboard, uma placa de ensaio com furos e conexões para testes e para
montagem dos componentes em protótipos, podendo ser substituída por uma placa de circuito
impresso simples.

## Funcionamento

Este funciona de forma simples, decidindo a senha e a colocando no Arduino através
de conexão com computador e trabalho com IDE, o sistema está pronto pra uso, ao clicar em
qualquer botão do teclado matricial, o buzzer é acionado para se ter uma confirmação do
clique, o que é clicado é gravado pelo Arduino que vai funcionar como um “comparador” e
verificar se a senha digitada é a mesma do que a inserida em seu código. Se a senha conferir,

é acionado o relé que muda de posição e permite passar energia para o sistema a ser acionado.
Ex: Ao acertar senha, o relé libera energia que ativa e abre uma fechadura eletrônica.
O buzzer e os Leds estão para dar auxílio e facilitar o uso do sistema.
Uma vez aberto, um tempo começa a correr, após este tempo o circuito se reinicia, no
exemplo, a porta se fecha novamente.

## Instalação

Por ter poucos componentes a instalação é fácil, após fazer as conexões dos pinos do
Arduino conforme indicado no guia de conexões, juntando os Leds com seus resistores e o
negativo na saída GND do Arduino para alimentação. O teclado matricial pode ser colado
onde for melhor para o usuário, na forma que foi feito este projeto, recomenda se manter o
Arduino em um local de fácil acesso, pois para reiniciar o sistema ou alguma eventual
mudança, é necessário acesso a ele.
É necessário alimentação tanto para o Arduino quanto para o resto do circuito, o
Arduino podendo ser alimentado por sua entrada USB ou pelo Pino Vin
O resto do circuito precisa de alimentação 12V, como utilizamos um relé para
liberação de passagem de energia, o positivo vai direto no relé e o negativo vai direto no
circuito externo, exemplo: Direto na fechadura eletrônica. Esta alimentação podendo ser feita
por uma fonte, com especificações de 0 e 12V

---
## Qualquer dúvida estamos a disposição

## João Gabriel


 jgrahmachado@gmail.com
 
---

## Valter Rogério

valterr28@gmail.com


[Github Valter](https://github.com/valterr28) 

