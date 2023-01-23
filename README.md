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
    <li>8x8 LED Dot Matrix with MAX7219 Controller<p align='center'><img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAzMCAyMCIgaGVpZ2h0PSIyMG1tIiB3aWR0aD0iMzBtbSIgeG1sbnM6eGxpbms9Imh0dHA6Ly93d3cudzMub3JnLzE5OTkveGxpbmsiPgogIDxzdHlsZSB0eXBlPSJ0ZXh0L2NzcyI+CiAgICAubGVkIHsKICAgICAgZmlsbDogdmFyKC0tcGl4ZWwtY29sb3IsIHJlZCk7CiAgICAgIGFuaW1hdGlvbjogbGVkLW9mZnNldCAycyBzdGVwcygyMCwganVtcC1lbmQpIGluZmluaXRlOwogICAgICBvZmZzZXQtcGF0aDogcGF0aCgnTTcuNSAyLjVIMjBNMjIuNSAyLjVWMTVNMjIuNSAxNy41SDEwTTcuNSAxNy41VjUnKTsKICAgICAgb2Zmc2V0LWRpc3RhbmNlOiAwJTsKICAgIH0KCiAgICBAa2V5ZnJhbWVzIGxlZC1vZmZzZXQgewogICAgICBmcm9tIHsKICAgICAgICBvZmZzZXQtZGlzdGFuY2U6IDAlOwogICAgICB9CiAgICAgIHRvIHsKICAgICAgICBvZmZzZXQtZGlzdGFuY2U6IDEwMCU7CiAgICAgIH0KICAgIH0KICA8L3N0eWxlPgogIDxkZWZzPgogICAgPHBhdHRlcm4gaWQ9ImJhY2tncm91bmQiIHdpZHRoPSIyLjUiIGhlaWdodD0iMi41IiBwYXR0ZXJuVW5pdHM9InVzZXJTcGFjZU9uVXNlIj4KICAgICAgPHJlY3Qgd2lkdGg9IjIuNSIgaGVpZ2h0PSIyLjUiIC8+CiAgICAgIDxjaXJjbGUgY3g9IjEuMjUiIGN5PSIxLjI1IiByPSIwLjkiIGZpbGw9IiM0NDQiIC8+CiAgICA8L3BhdHRlcm4+CiAgICA8cGF0aAogICAgICBpZD0icGlubCIKICAgICAgZmlsbD0iI2M2YmY5NSIKICAgICAgZD0ibTcuMDItMC4zOWgtNy4wMmEwLjM5IDAuMzkgMCAwIDAtMC4zNyAwLjM5IDAuMzkgMC4zOSAwIDAgMCAwLjM3IDAuMzl2MGg3LjAyeiIKICAgIC8+CiAgICA8cGF0aAogICAgICBpZD0icGluciIKICAgICAgZmlsbD0iI2M2YmY5NSIKICAgICAgZD0ibS03LjAyLTAuMzloNy4wMmEwLjM5IDAuMzkgMCAwIDEgMC4zNyAwLjM5IDAuMzkgMC4zOSAwIDAgMS0wLjM3IDAuMzl2MGgtNy4wMnoiCiAgICAvPgogIDwvZGVmcz4KICA8dXNlIHhsaW5rOmhyZWY9IiNwaW5sIiB4PSIwLjUzIiB5PSI0LjkyIiAvPgogIDx1c2UgeGxpbms6aHJlZj0iI3BpbmwiIHg9IjAuNTMiIHk9IjcuNDYiIC8+CiAgPHVzZSB4bGluazpocmVmPSIjcGlubCIgeD0iMC41MyIgeT0iMTAiIC8+CiAgPHVzZSB4bGluazpocmVmPSIjcGlubCIgeD0iMC41MyIgeT0iMTIuNTQiIC8+CiAgPHVzZSB4bGluazpocmVmPSIjcGlubCIgeD0iMC41MyIgeT0iMTUuMDgiIC8+CiAgPHVzZSB4bGluazpocmVmPSIjcGluciIgeD0iMjkuNDciIHk9IjQuOTIiIC8+CiAgPHVzZSB4bGluazpocmVmPSIjcGluciIgeD0iMjkuNDciIHk9IjcuNDYiIC8+CiAgPHVzZSB4bGluazpocmVmPSIjcGluciIgeD0iMjkuNDciIHk9IjEwIiAvPgogIDx1c2UgeGxpbms6aHJlZj0iI3BpbnIiIHg9IjI5LjQ3IiB5PSIxMi41NCIgLz4KICA8dXNlIHhsaW5rOmhyZWY9IiNwaW5yIiB4PSIyOS40NyIgeT0iMTUuMDgiIC8+CiAgPHJlY3QgeD0iNSIgd2lkdGg9IjIwIiBoZWlnaHQ9IjIwIiBmaWxsPSJ1cmwoI2JhY2tncm91bmQpIiAvPgogIDxjaXJjbGUgY3g9IjEuMjUiIGN5PSIxLjI1IiByPSIwLjkiIGZpbGw9InJlZCIgY2xhc3M9ImxlZCIgLz4KPC9zdmc+Cg==" alt="Screen" width="389" height="72"></p></li> 
    <li>Arduino Uno.<p align='center'><img src="https://upload.wikimedia.org/wikipedia/commons/7/7c/Arduino_Uno_%28Versi%C3%B3n_Inform%C3%A1tica%29.png" alt="Screen" width="417" height="212"></p></li> 
</ul>
      <p>Clique <a href="https://wokwi.com/projects/354649261697701889">nesse link</a> e você será redirecionado ao projeto no Wokwi. Onde já esta os componentes e sua respectivas conexões.</p>
    <h3>Conexões</h3>
      <p>As conxões do outro lado do modulo do Led não serão feitas pois nosso objetivo é usar apenas uma matriz de 8x8 mas se você quisesse ligar mais de uma ai sim isso seria necessário.</p>
      <p align='center'><table border="1">
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