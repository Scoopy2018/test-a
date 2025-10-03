<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Anniversary Slide</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body, html {
      width: 100%;
      height: 100%;
      font-family: 'Poppins', sans-serif;
      overflow: hidden;
    }

    .slide {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-size: cover;
      background-position: center;
      display: flex;
      justify-content: center;
      align-items: center;
      transition: opacity 1s ease-in-out;
    }

    /* Slide pertama */
    #slide1 {
      background-image: url('poto 1.jpeg'); /* foto annisa */
      opacity: 1;
      z-index: 2;
    }

    /* Slide kedua */
    #slide2 {
      background-image: url('Kertas.jpg.jpg'); /* foto kertas */
      opacity: 0;
      z-index: 1;
      padding: 30px;
      text-align: center;
      color: #333;
      overflow-y: auto;
    }

    .text-box {
      background: transparent;        /* hilangkan background putih */
      border-radius: 15px;           /* tetap tepi bulat */
      padding: 25px;
      max-width: 90%;
      font-size: 1rem;
      line-height: 1.7;
      margin: 20px auto;
      white-space: pre-line;         /* biar enter di text kebaca */
      text-align: left;
      color: #222;                   /* tulisan tetap kelihatan */
      text-shadow: 1px 1px 3px rgba(0,0,0,0.3); /* biar terbaca di atas background */
    }

    .text-box h2 {
      text-align: center;
      font-size: 1.3rem;
      font-weight: bold;
      margin-bottom: 15px;
      color: #222;
      text-shadow: 1px 1px 3px rgba(0,0,0,0.3); /* konsisten dengan teks */
    }

    button {
      padding: 12px 24px;
      background: #222;
      color: white;
      border: none;
      border-radius: 50px;
      font-size: 1rem;
      cursor: pointer;
      transition: transform 0.2s ease, background 0.3s ease;
      position: relative;
      overflow: hidden;
      text-transform: lowercase;
    }

    button:hover {
      background: #444;
      transform: scale(1.1);
    }

    /* Efek bintang aesthetic */
    button::after {
      content: '✨';
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%) scale(0);
      opacity: 0;
      transition: transform 0.3s ease, opacity 0.3s ease;
    }

    button:active::after {
      transform: translate(-50%, -50%) scale(1.5);
      opacity: 1;
    }
  </style>
</head>
<body>
  <!-- Slide Pertama -->
  <div id="slide1" class="slide">
    <button onclick="nextSlide()">tap me ✨</button>
  </div>

  <!-- Slide Kedua -->
  <div id="slide2" class="slide">
    <div class="text-box">
      <h2>Our First Chapter</h2>
      <div id="typewriter"></div>
    </div>
  </div>

  <script>
    const text = `cerita kita dari awal ketemu tuh bener-bener kayak roller coaster — full of colors, ups and downs, tapi selalu worth it. kadang kita ketawa sampe sakit perut, kadang ada drama kecil, tapi semua itu bikin kita makin kuat dan makin ngerti satu sama lain. honestly, i feel so lucky spending this year with you, karena kamu bukan cuma pacar pertama aku, tapi juga my first love — the one who taught me what love really feels like.

we both tried, we both cared. even when we stumbled at the end, it doesn’t mean our story is done. one year with you, annisa puji wulandari, showed me that love isn’t about being perfect, but about choosing each other again and again. kita pernah janji buat jalan bareng, and i still believe in that. no matter how hard it gets, aku bakal selalu pilih kamu, over and over, in every lifetime.

this one year feels like a book full of stories — some pages messy, some beautiful, tapi setiap halaman milik kita. dari jokes receh sampai obrolan dalem, semuanya priceless. being with you makes me realize, love isn’t only about big moments, tapi juga hari-hari biasa yang jadi special just because you’re there.

and you know what? kamu itu literally the prettiest plot twist in my life. like, how did i get so lucky to have you as my first love? kalau ini baru chapter pertama, i can’t wait to see the rest of our story — with you always by my side.

p.s: jangan geer dulu sih, tapi kayanya semesta emang pengen kita bikin season 2 bareng 😏

— fathi`;

    let i = 0;
    const speed = 60; // kecepatan ketikan (ms)

    function typeWriter() {
      if (i < text.length) {
        document.getElementById("typewriter").innerHTML += text.charAt(i);
        i++;
        setTimeout(typeWriter, speed);
      }
    }

    function nextSlide() {
      document.getElementById("slide1").style.opacity = 0;
      document.getElementById("slide2").style.opacity = 1;
      setTimeout(typeWriter, 1000); // mulai ketik setelah 1 detik
    }
  </script>
</body>
</html>
