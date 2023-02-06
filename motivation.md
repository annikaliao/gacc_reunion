Helping you stay MOTIVATED and ENERGIZED!

<!DOCTYPE html>
<html>
  <head>
    <title>Random Quote Generator</title>
  </head>
  <body>
    <h1>Random Quote</h1>
    <p id="quote"></p>
    <button onclick="getQuote()">Get Quote</button>
    <script>
      function getQuote() {
        var xhr = new XMLHttpRequest();
        xhr.open('GET', 'https://quotes-inspirational-quotes-motivational-quotes.p.rapidapi.com/quote?token=ipworld.info%27);
        xhr.setRequestHeader("X-RapidAPI-Key", "f0aeb431bamshc18b522b64e7383p102f67jsnea4673acfc55");
        xhr.setRequestHeader("X-RapidAPI-Host", "quotes-inspirational-quotes-motivational-quotes.p.rapidapi.com");
        xhr.onload = function() {
          if (xhr.status === 200) {
            var quote = JSON.parse(xhr.responseText);
            document.getElementById("quote").innerHTML = quote.quote;
          } else {
            document.getElementById("quote").innerHTML = "Error: Unable to retrieve quote.";
          }
        };
        xhr.send();
      }
    </script>
  </body>
</html>