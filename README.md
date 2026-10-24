
<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mój Własny Telewizor</title>
    <!-- Nowoczesny odtwarzacz wideo Video.js -->
    <link href="https://zencdn.net" rel="stylesheet" />
    <style>
        body { font-family: 'Segoe UI', Arial, sans-serif; background: #141414; color: white; text-align: center; padding: 20px; margin: 0; }
        .container { max-width: 900px; margin: 0 auto; padding: 20px; }
        h1 { color: #e50914; font-size: 2.5rem; margin-bottom: 5px; }
        .video-js { margin: 20px auto; width: 100%; height: 500px; border-radius: 8px; box-shadow: 0px 4px 20px rgba(0,0,0,0.5); }
        .playlist { display: flex; justify-content: center; gap: 12px; margin-top: 25px; flex-wrap: wrap; }
        button { background: #222; color: white; border: 2px solid #444; padding: 12px 24px; cursor: pointer; border-radius: 6px; font-size: 16px; font-weight: bold; transition: 0.2s; }
        button:hover { background: #e50914; border-color: #e50914; transform: scale(1.05); }
    </style>
</head>
<body>

<div class="container">
    <h1>Mój Telewizor 📺</h1>
    <p>Wybierz polski kanał z listy poniżej i oglądaj:</p>

    <!-- Główny ekran telewizora -->
    <video id="tv-player" class="video-js vjs-default-skin vjs-big-play-centered" controls preload="auto" data-setup="{}">
        <source src="https://stars.tv" type="application/x-mpegURL">
    </video>

    <!-- Lista polskich kanałów (tutaj możesz dopisywać kolejne przyciski) -->
    <div class="playlist">
        <button onclick="zmienKanal('https://stars.tv')">Stars.TV (Muzyka)</button>
        <button onclick="zmienKanal('https://tvregionalna.pl')">TV Regionalna (Informacje)</button>
        <button onclick="zmienKanal('https://tvt.pl')">Telewizja TVT (Lokalny)</button>
    </div>
</div>

<!-- Skrypty odpowiedzialne za działanie telewizora i przełączanie stacji -->
<script src="https://zencdn.net"></script>
<script>
    function zmienKanal(linkURL) {
        var player = videojs('tv-player');
        player.src({ src: linkURL, type: 'application/x-mpegURL' });
        player.play();
    }
</script>

</body>
</html>
