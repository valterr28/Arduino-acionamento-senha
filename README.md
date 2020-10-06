# PROJETO LGP ARDUINO


João Gabriel Grah Machado
Valter Rogério da Silva Júnior
622
Lógica da programação - Carlos Speranza



## Links

[Github](https://github.com/valterr28/Arduino-acionamento-senha)
[Fluxograma](https://)
[Código](https://drive.google.com/file/d/1keEei7JQ_Fq-lYnQXb5YXb-tzqS21Ci-/view?usp=sharing)
[Guia de Conexões](https://drive.google.com/file/d/18Dcz624WUKtDAnQRxaulzMFy0aoJImCS/view?usp=sharing)
[Relatório escrito do projeto](https://drive.google.com/file/d/17sE5uPrXecWP6FvEGLbqAQpM0q4Be4Yi/view?usp=sharing)
[Vídeo - Drive](https://)




```csharp=
/*  Controle de acesso por senha  
   
   Criado por: João Gabriel e Valter Rogério
   Turma: 622
   Setembro de 2020
         
 */


#include <Keypad.h> // Biblioteca do módulo teclado

/************************ Escolha da Senha ******************************* */

char* senha = "ABC123";  // defina a senha aqui, ela deve conter seis dígitos podendo repetir 

/************************ Teclado ******************************* */

const byte LINHAS = 4; // quantidade de linhas do teclado
const byte COLUNAS = 4; // quantidade de colunas do teclado

char digitos[LINHAS][COLUNAS] = {
{'1','2','3','A'},
{'4','5','6','B'},
{'7','8','9','C'},
{'*','0','#','D'}}; // Caracteres do teclado 

byte pinosLinha[LINHAS] = { 11, 10, 9, 8 }; // Pinos das linhas no arduino 
byte pinosColuna[COLUNAS] = { 7, 6, 5, 4 }; // Pinos das colunas no arduino 

Keypad keypad = Keypad( makeKeymap(digitos), pinosLinha, pinosColuna, LINHAS, COLUNAS ); // objeto de leitura das teclas com os parâmetros lidos

/************************ VARIÁVEIS AUXILIARES ******************************* */

int position = 0;
int ledVermelho = 12;
int ledVerde = 13;
int releFechadura = 3; //led azul substituir por módulo relé
int buzzer = 2;
int tempoBuzz = 50;
int tempoAberto = 2000; //Determina o tempo que o sistema mantém o estado após acerto de senha e abertura da porta

/***************************************************************************** */

void setup()
{ 
  
estadoPorta(true); // diz se a porta está ou não trancada

    //define os pinos de saída do arduino

pinMode(ledVermelho,OUTPUT); //Led de funcionamento
pinMode(ledVerde,OUTPUT); //Led de sucesso
pinMode(releFechadura,OUTPUT); //Relé que abre sistema
pinMode(buzzer,OUTPUT); // Buzzer para som de funcionamento e alarme

}

void loop()
{
  
char digito = keypad.getKey(); // faz a leitura das teclas

if (digito !=0) // Quando diferente de 0 acionar este código
{
  digitalWrite(buzzer, HIGH);
  delay(tempoBuzz);
  digitalWrite(buzzer, LOW); // acionamento do buzzer ao apertar qualquer tecla para noção de clique

if (digito == senha[position]) // verifica se o dígito apertado corresponde ao equivalente da senha
{
position ++;
}
else { // retorna a leitura para a primeira posição de leitura da senha quando o dígito apertado não corresponde ao correto para uma nova tentativa
position = 0;
}
if (position == 6) // altera estado da porta  
{
estadoPorta(false);
}
delay(100);
}
}

void estadoPorta(int trancado)
{
  
if (trancado) // trancamento da porta
{
digitalWrite(ledVermelho, HIGH); //Led vermelho ligado mostrando que está fechada
digitalWrite(ledVerde, LOW); //Led verde desligado mostrando que não foi aberta ainda
digitalWrite(releFechadura, LOW); // importante: para uso com rele de acionamento da fechadura LOW deve ser subsstituído por HIGH
}

else // abertura da porta
{
digitalWrite(ledVermelho, LOW); //Led vermelho desliga
digitalWrite(ledVerde, HIGH); //Led verde acende mostrando sucesso do sistema 
digitalWrite(releFechadura, HIGH); // importante: para uso com rele de acionamento da fechadura HIGH deve ser subsstituído por LOW
digitalWrite(buzzer, HIGH); //Buzzer toca para também indicar funcionamento
delay(tempoBuzz*10);
digitalWrite(buzzer, LOW); // buzzer indica o acerto da senha 
delay(tempoAberto);
position = 0;
digitalWrite(releFechadura, HIGH);
estadoPorta(true); // tranca a porta novamente 
}
}
```


---
## Qualquer dúvida estamos a disposição

## João Gabriel


 jgrahmachado@gmail.com
 
---

## Valter Rogério

valterr28@gmail.com


[Github Valter](https://github.com/valterr28) 

