# Owlficina - Microcontroladores ESP32

```Este é o template básico do relatório do curso. Fique à vontade para adicionar mais tópicos, mas preencha todos os tópicos que estão aqui! Este documento está em markdown, mas fique à vontade para criar um documento de texto, desde que contenha os mesmos tópicos. Sugerimos que subam o código e o relatório (como README.md) no github ou, caso não seja possível, código e github como uma pasta zipada no final do curso.```


<p align="center">
  <img src="https://media.elektor.com/media/catalog/product/cache/9cc822bfc6a57f9729d464b8b5e0e0df/j/o/joy-it-nodemcu-esp32-development-board_front.png" width="300" /><br/>
Nome do projeto <br/>
</p>

<br/>

## :pushpin: Descrição

O que é o seu projeto? Qual o objetivo do sistema?
Não precisa colocar muitas informações técnicas aqui, só deixe sua ideia clara :)


<br/>

## :robot: Montagem do dispositivo físico

### Lista de materiais

| Quantidade | Nome | Link para referência |
| --- | --- | --- |
| 1 | ESP32 e cabo USB | https://www.baudaeletronica.com.br/placa-doit-esp32-bluetooth-e-wifi.html |
| 1 | Buzzer ativo programável | https://www.eletrogate.com/buzzer-ativo-5v?utm_source=Site&utm_medium=GoogleMerchant&utm_campaign=GoogleMerchant&gad=1&gclid=Cj0KCQjwk96lBhDHARIsAEKO4xauBy1Zdvprys4j1ThOaqRjedv45X4-ec5x3n0ZeytOvHP0reTzkQkaAu_0EALw_wcB |
| 1 | Sensor de distância ultrassônico HC-SR04 | https://www.baudaeletronica.com.br/produto/sensor-de-distancia-ultrassonico-hc-sr04.html |
| 1 | NeoPixel Led RGB (WS2812) | https://pt.aliexpress.com/item/1005001971806517.html?src=google |
| X | Jumpers variados | --- |
| 1 | Protoboard | --- |
| 1 | Fonte de alimentação - PowerBank | https://www.americanas.com.br/produto/2706391331 |

#### ❕ Disclaimer
O Led RGB utilizado neste circuito é diferente do que se encontra na imagem do circuito e também da referência

### Lista de conexões

| Componente | Pino da placa |
| --- | --- |
| Sensor de Distância (Trigger) | 5 |
| Sensor de Distância (Echo) | 4 |
| Led RGB | 13 |
| Buzzer | 15 |


### Funcionamento dos sensores e atuadores

#### Sensor de distância ultrassônico HC-SR04

Para começar uma medida, o pino TRIG do módulo deve receber um pulso alto, ou seja, 5V do microcontrolador por pelo menos 10us, isso vai iniciar o sensor, o qual vai enviar 8 ciclos de sinal ultrasônico a 40kHz e esperar pelo mesmo sinal refletido. Quando o sensor detecta o sinal de volta, ele vai setar o pino ECHO em nível lógico alto, ou seja, 5V e vai esperar por um período que é proporcional à distância. Para obter a distância, basta medir o tempo que o pino Echo fica com nível lógico alto, ou seja:

Tempo = Largura do Pulso em Echo, em micro segundos

Logo, Distância em centímetros = Tempo / 58

ou Distância em polegadas = Tempo / 148

Ou você pode usar a velocidade do som, que é de 340m/s.

(Especificação técnica: https://d229kd5ey79jzj.cloudfront.net/620/HCSR04.pdf)

Suas principais características são: 

- Tensão de Alimentação: 5VDC;
- Corrente quiescente: < 2mA;
- Corrente em funcionamento: 15mA;
- Ângulo de medida: < 15°;
- Distância de detecção: de 2cm a 400cm;
- Resolução: 3mm;
- Dimensões: 45mm x 20mm x 15mm;
- Frequência ultrasônica: 40kHz;


#### Sensor de toque TTP223B
O Módulo LED RGB KY-016 foi desenvolvido para facilitar projetos que necessitam de um LED RGB em sua composição. Este módulo dispensa o uso de resistores para utilizá-lo por já conter em sua PCB os resistores necessários para manter o funcionamento do LED correto e seguro.

Trazendo uma grande versatilidade no desenvolvimento dos projetos, o Módulo LED RGB KY-016 conta com 4 pinos, sendo eles 3 pinos para as conexões do LED: Vermelho, Verde e Azul, e um pino de GND com símbolo de "-" na placa para conexão do GND do microcontrolador ou fonte de alimentação.

O sensor digital de toque TTP223B é de simples funcionamento, mudando o sinal quando há um toque. Sua tensão de operação é entre 2-5, 5V; a saída de estado alto é 0,8V e baixo de 0,3 V. O tempo de resposta é de 220 ms (em estado baixo) e 60 ms (em estado alto), contando com as dimensões de 24 x 24 x 7,2 mm (Especificação técnica: https://files.seeedstudio.com/wiki/Grove-Touch_Sensor/res/TTP223.pdf)


### Circuito

<p align="center">
Figura - Diagrama do circuito<br/>
  <img src="Circuito.JPG" width="400" /><br/>
</p>
Os fios pretos foram usados para representar a conexão com pino GND;

Os fios vermelhos foram usados para representar a conexão de alimentação do componente;

Informações importantes sobre o circuito, onde colocá-lo, entre outros.
<br/>

<br/>

## :electric_plug: Funcionamento do sistema

**Não esqueça: adicione um videozinho do sistema funcionando :)**

Liste informações como:
- requisitos do código
- estrutura de arquivos
- qual o objetivo de cada arquivo/pedaço de código
Não precisa ser muito detalhado, apenas o suficiente para que seu código seja entendível!


<br/>

## :busts_in_silhouette: Contribuir no projeto

### Features implementadas

- [x] Buzzer programado com diferentes frequências e com diferentes frequências de beeps;
- [x] Led RGB piscando diferentes cores;
- [x] Sensor de presença que pega uma distância em mm;
- [x] Emitir uma frequência de som e luz ao detectar uma presença dentro de um determinado intervalo
- [x] Identificação da mudança de posição na cadeira *(exemplo de features que já estão funcionando no projeto)*


### Features para incrementar no projeto

- [ ] Implementar uma tela OLed para apresentar uma mensagem em alguma distância;
- [ ] Emitir ritmos músicais com o Buzzer;
- [ ] Possibilidade do usuário configurar o tempo e a temperatura para os alertas *(exemplo de features que as pessoas podem contribuir no projeto)*

