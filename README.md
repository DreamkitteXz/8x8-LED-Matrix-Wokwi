<h2 align='center'>
  Testando a plataforma Wokwi 
</h2>
<h3>
  Visão geral 
</h3>
<p>
  <p>Wokwi é um simulador de Eletrônica online. Você pode usá-lo para simular Arduino, ESP32 e muitas outras placas, peças e sensores populares. Iremos fazer uma carinha feliz na matrix de led 8x8 no Wokwi e depois testar na prática para ver se funciona.</p>
<p>Visite esse <a href="https://embarcados.com.br/wokwi-simulador-de-esp32/#O-que-e-o-Wokwi
">artigo</a> se voçê quiser saber mais sobre a plataforma.</p>
</p>
<p>
Voce ira aprender:
<ul>
    <li>Instalar uma biblioteca no Wokwi</li>  
</ul>

  <h2 align='center'>Começando...</h2>
      <h3>Componentes utilizados</h3>
      <ul>
    <li>8x8 LED Dot Matrix with MAX7219 Controller<p align='center'><img src="https://raw.githubusercontent.com/gist/DreamkitteXz/f73cf72a38741b16a3b242c1f9c6d438/raw/3cb9e826bdac35c51cb7cfd657911a2fa0955045/download.svg" alt="Screen" width="389" height="72"></p></li> 
    <li>Arduino Uno.<p align='center'><img src="https://upload.wikimedia.org/wikipedia/commons/7/7c/Arduino_Uno_%28Versi%C3%B3n_Inform%C3%A1tica%29.png" alt="Screen" width="417" height="212"></p></li> 
</ul>
      <p>Clique <a href="https://wokwi.com/projects/354649261697701889">nesse link</a> e você será redirecionado ao projeto no Wokwi. Onde já esta os componentes e sua respectivas conexões.</p>
    <h3>Conexões</h3>
      <p>As conxões do outro lado do modulo do Led não serão feitas pois nosso objetivo é usar apenas uma matriz de 8x8 mas se você quisesse ligar mais de uma ai sim isso seria necessário.</p>
      <table border="3" align='center'>
    <tr>
        <td><b>Pinos Led</b></td>
        <td><b>Pinos Arduino</b></td>
    </tr>
    <tr>
        <td align='center'>VCC</td>
        <td align='center'>5V</td>
    </tr>
    <tr>
        <td align='center'>GND</td>
        <td align='center'>GND</td>
    </tr>
    <tr>
        <td align='center'>DIN</td>
        <td align='center'>Pin 12</td>
    </tr>
    <tr>
        <td align='center'>CS</td>
        <td align='center'>pin 10</td>
    </tr>
    <tr>
        <td align='center'>CLK</td>
        <td align='center'>pin 11</td>
    </tr>
</table>
<h3>Emoji</h3>
<p> Logo abaixo tem o código que mostra um Emoji sorrindo, mas antes de executarmos esse código temos que instalar a biblioteca <code>LedControl.h</code> para o código funcionar. Para fazer isso é muito facil, basta você clicar em <code>Library Manager</code> e pesquisar por <code>LedControl</code>.
</p>
<img src="Library.png" alt="Screen" width="900" height="400">
<h3 align='center'>Código</h3>
<p > Agora execute o código:</p>
<p align='center'><pre><code >

#include "LedControl.h"
#include "binary.h"

/*
 DIN conectado no pino 12
 CLK conectado no pino 11
 CS conectado no pino 10 
*/
LedControl lc=LedControl(12,11,10,1);

// Tempo de delay entre as caras
unsigned long delaytime=1000;

// cara feliz
byte hf[8]= {B00111100,B01000010,B10100101,B10000001,B10100101,B10011001,B01000010,B00111100};
// cara neutra
byte nf[8]={B00111100, B01000010,B10100101,B10000001,B10111101,B10000001,B01000010,B00111100};
// cara triste
byte sf[8]= {B00111100,B01000010,B10100101,B10000001,B10011001,B10100101,B01000010,B00111100};

void setup() {
  lc.shutdown(0,false);
  // Brilho médio
  lc.setIntensity(0,8);
  // Limpa o display
  lc.clearDisplay(0);  
}

void drawFaces(){
  // Mostra a cara trite
  lc.setRow(0,0,sf[0]);
  lc.setRow(0,1,sf[1]);
  lc.setRow(0,2,sf[2]);
  lc.setRow(0,3,sf[3]);
  lc.setRow(0,4,sf[4]);
  lc.setRow(0,5,sf[5]);
  lc.setRow(0,6,sf[6]);
  lc.setRow(0,7,sf[7]);
  delay(delaytime);
  
  // Mostra a cara neutra
  lc.setRow(0,0,nf[0]);
  lc.setRow(0,1,nf[1]);
  lc.setRow(0,2,nf[2]);
  lc.setRow(0,3,nf[3]);
  lc.setRow(0,4,nf[4]);
  lc.setRow(0,5,nf[5]);
  lc.setRow(0,6,nf[6]);
  lc.setRow(0,7,nf[7]);
  delay(delaytime);
  
  // Mostra a cara feliz
  lc.setRow(0,0,hf[0]);
  lc.setRow(0,1,hf[1]);
  lc.setRow(0,2,hf[2]);
  lc.setRow(0,3,hf[3]);
  lc.setRow(0,4,hf[4]);
  lc.setRow(0,5,hf[5]);
  lc.setRow(0,6,hf[6]);
  lc.setRow(0,7,hf[7]);
  delay(delaytime);
}

void loop(){
  drawFaces();
}</code></pre></p>
<p>Espere o seguinte resultado:</p>
<p align='center'><img src="ezgif.com-gif-maker (5).gif" alt="Screen" width="600" height="337">
<h3 align='center'>
  Testando na prática
</h3>
<p>
  <p>Agora vamos testar na prática o que fizemos no simulador, iremos precisar dos mesmos componentes e serão as mesmas conexões e utilizaremos o Arduino IDE.</p>
<p>1. Monte seu circuito na prática fazendo as mesmas conexões</p>
<p>2. Copie e cole o código para o Arduino IDE.</p>
<p>3. Selecione a porta <code>COM</code></p>
<p>4. Execute o código.</p>
<p align='center'><img src="arduino.gif.gif" alt="Screen" width="600" height="337">
<p> Espere o seguinte resultado:</p>
<img src="Happy.gif" alt="Screen" width="600" height="1067">