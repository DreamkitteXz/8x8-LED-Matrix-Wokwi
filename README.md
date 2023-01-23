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
</table></p>