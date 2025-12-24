# Comic-presentations-
Comic launch 🚀 
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Shlok Kamle • Art & Comics</title>

  <!-- GitHub Pages compatible CSS -->
  <style>
    :root{
      --bg:#f5f5f7;
      --card:#ffffff;
      --text:#111;
      --muted:#6e6e73;
      --accent:#007aff;
      --shadow:0 8px 30px rgba(0,0,0,.08);
    }
    body.dark{
      --bg:#1c1c1e;
      --card:#2c2c2e;
      --text:#f2f2f7;
      --muted:#8e8e93;
      --accent:#0a84ff;
    }
    *{box-sizing:border-box;font-family:-apple-system,BlinkMacSystemFont,'Segoe UI',Roboto,Arial}
    body{margin:0;background:var(--bg);color:var(--text)}
    header{text-align:center;padding:48px 20px}
    h1{font-size:3rem;font-weight:800;margin:0}
    .sub{color:var(--muted);margin-top:8px}
    .toggle{position:absolute;top:20px;right:20px}
    button{background:var(--accent);color:white;border:none;border-radius:999px;padding:10px 18px;font-weight:600;cursor:pointer}
    .container{max-width:1100px;margin:auto;padding:20px}
    .card{background:var(--card);border-radius:28px;padding:28px;margin-bottom:24px;box-shadow:var(--shadow)}
    .countdown{display:flex;justify-content:center;gap:30px;font-size:2.5rem;font-weight:800}
    .countdown div{text-align:center}
    .countdown span{display:block;font-size:0.9rem;color:var(--muted)}
    .gallery{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:20px}
    .gallery img{width:100%;border-radius:18px;box-shadow:var(--shadow)}
    footer{text-align:center;padding:30px;color:var(--muted)}
    input[type="date"],input[type="password"]{padding:12px;border-radius:14px;border:1px solid #ccc;width:100%}
    .admin{display:none;margin-top:16px}
  </style>
</head>

<body>
  <header>
    <button class="toggle" onclick="toggleMode()">🌙 / ☀️</button>
    <h1>Art & Comics Launch 🚀</h1>
    <div class="sub">Countdown to something special</div>

    <div class="countdown" id="countdown">
      <div><div id="d">00</div><span>Days</span></div>
      <div><div id="h">00</div><span>Hours</span></div>
      <div><div id="m">00</div><span>Minutes</span></div>
    </div>
  </header>

  <div class="container">

    <div class="card">
      <label><strong>Launch Date</strong></label>
      <input type="date" id="launchDate" />
    </div>

    <div class="card">
      <h2>🎨 Art & Comics Gallery</h2>
      <div class="gallery" id="gallery"></div>
    </div>

    <div class="card">
      <h2>🔐 Admin (Only You)</h2>
      <input type="password" id="pass" placeholder="Enter admin password" />
      <button onclick="login()">Unlock</button>

      <div class="admin" id="admin">
        <input type="file" accept="image/*" onchange="upload(event)" />
        <p class="sub">Images save in your browser (GitHub Pages safe)</p>
      </div>
    </div>

    <div class="card">
      <h2>🙋 About Me</h2>
      <p>
        I am <strong>Shlok Kamle</strong>. I studied in Higher Secondary. I have made many comics and artworks and to show it I have coded this website which portrays my art & skills in drawing.
      </p>
    </div>

  </div>

  <footer>
    Made with love ❤️<br>By Shlok Kamle
  </footer>

  <!-- GitHub Pages SAFE JavaScript -->
  <script>
    function toggleMode(){document.body.classList.toggle('dark')}

    const launch=document.getElementById('launchDate')
    setInterval(()=>{
      if(!launch.value) return
      const diff=new Date(launch.value)-new Date()
      if(diff<=0) return
      document.getElementById('d').innerText=Math.floor(diff/86400000)
      document.getElementById('h').innerText=Math.floor(diff/3600000)%24
      document.getElementById('m').innerText=Math.floor(diff/60000)%60
    },1000)

    function login(){
      if(document.getElementById('pass').value==='shlok123'){
        document.getElementById('admin').style.display='block'
      }
    }

    function upload(e){
      const img=document.createElement('img')
      img.src=URL.createObjectURL(e.target.files[0])
      document.getElementById('gallery').appendChild(img)
    }
  </script>
</body>
</html>
