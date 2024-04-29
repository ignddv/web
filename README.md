<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Belmontejo</title>
</head>
<body>
    <header>
            <h1>Castilla la Mancha</h1>
            <nav>
                <a href="index.html">Inicio</a>
                <a href="index2.html">Mapa</a>
            </nav>
    </header>
    <style>
        body{
            background-color: #008080;
            text-align: center;
        }
        a{
            color: black;
        }
        header{
            background-color: #424949;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 10px;
        }
        nav a{
            text-decoration: none;
            font-weight: 600px;
            padding-right: 10px;    
        }
        .container1{
            text-align: center;
            font-style: italic;
        }
        h2{
            text-decoration: underline;

        }
        img{
            align-items: center;
        }
        .audio{
            align-items: center;
        }
    </style>
    <div class="container1">
        <h2>El pueblo más bonito: Belmontejo</h2>
        <p>
            Belmontejo es un municipio y localidad española de la provincia de Cuenca, en la comunidad autónoma de Castilla-La Mancha.
            El término municipal tiene una población de 135 habitantes.
            Integrado en la comarca de La Mancha Conquense, se sitúa a 45 km de la capital provincial. El término municipal está atravesado por la carretera N-420 entre los pK 388 y 393.

            El relieve del municipio se caracteriza por presentar muchas ondulaciones del terreno, además de contar con la presencia del río Marimota que desemboca en el embalse de Alarcón, que hace de límite con Albaladejo del Cuende.
            La altitud oscila entre los 968 m al norte y los 820 m a orillas del embalse. Al sur, destaca el cerro Cardenal, que alcanza los 966 m. 
            El pueblo se alza a 878 m sobre el nivel del mar. 
        </p>
        <img src="Media/unnamed.jpg">
    </div>
    <div>
        <h2>Canción de Castilla la Mancha</h2>
        <audio src="Media/Audio.mp3" controls autoplay loop>Canción de Castilla la Mancha</audio>
    </div>
    <div class="container2">
        <h2>Demografía</h2>
        <p>
            Este gráfico muestra los habitantes de Belmontejo desde 1842 a 2021
            Se ve un claro descenso de la población rural no solo en Belmontejo 
            si no en todos los pueblos de alrededor debido al éxodo rural del 
            campo a la ciudad
        </p>
        <img src="Media/Demografía.png" alt="">
    </div>
    <div class="container2">
        <h2>Belmontejo en las noticias</h2>
        <iframe width="560" height="315" src="https://www.youtube.com/embed/a3HNBcmf4w0?si=_wPity1oNZqoO5ip" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
    </div>
    <a href="https://es.wikipedia.org/wiki/Belmontejo">Para más información pincha en este link</a>
    <div id="timer">Tiempo restante: <span id="time">60</span> segundos</div>
        <div id="questions">
          <div class="question">
            <p>1. ¿En qué distrito se encuentra el barrio de Aluche en Madrid?</p>
            <input type="text" id="answer1">
          </div>
          <div class="question">
            <p>2. ¿Qué río atraviesa el barrio de Aluche?</p>
            <input type="text" id="answer2">
          </div>
          <div class="question">
            <p>3. ¿Cuál es el nombre del parque más grande de Aluche?</p>
            <input type="text" id="answer3">
          </div>
          <div class="question">
            <p>4. ¿Qué estación de trenes y metro es una de las principales de Aluche?</p>
            <input type="text" id="answer4">
          </div>
          <div class="question">
            <p>5. ¿Cómo se llama el centro comercial que hay en Aluche?</p>
            <input type="text" id="answer5">
          </div>
        </div>
        <button onclick="submitAnswers()">Enviar respuestas</button>
        <div id="result"></div>
      
      <script>
        let timeLeft = 60;
        let timer = setInterval(() => {
          document.getElementById("time").innerText = timeLeft;
          timeLeft -= 1;
          if (timeLeft < 0) {
            clearInterval(timer);
            document.getElementById("time").innerText = "0";
            document.getElementById("result").innerText = "¡Tiempo agotado!";
          }
        }, 1000);
      
        function submitAnswers() {
          clearInterval(timer);
          let correctAnswers = 0;
          const answers = {
            answer1: document.getElementById("answer1").value.toLowerCase(),
            answer2: document.getElementById("answer2").value.toLowerCase(),
            answer3: document.getElementById("answer3").value.toLowerCase(),
            answer4: document.getElementById("answer4").value.toLowerCase(),
            answer5: document.getElementById("answer5").value.toLowerCase()
          };
          if (answers.answer1 === "la latina") {
            correctAnswers++;
          }
          if (answers.answer2 === "manzanares") {
            correctAnswers++;
          }
          if (answers.answer3 === "parque aluche") {
            correctAnswers++;
          }
          if (answers.answer4 === "aluche") {
            correctAnswers++;
          }
          if (answers.answer5 === "plaza aluche") {
            correctAnswers++;
          }
          document.getElementById("result").innerText = `Has obtenido ${correctAnswers} respuestas correctas de 5.`;
        }
      </script>
</body>
</html>
