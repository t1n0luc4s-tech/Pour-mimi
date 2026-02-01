# Pour-mimi
<!DOCTYPE html><html lang="fr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Pour Mimi</title>
  <style>
    :root{
      --red:#c1121f;
      --black:#0b0b0b;
      --white:#ffffff;
      --gray:#777;
    }
    *{box-sizing:border-box}
    body{
      margin:0;
      min-height:100vh;
      display:flex;
      align-items:center;
      justify-content:center;
      background:var(--white);
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
      color:var(--black);
    }
    .container{
      width:100%;
      max-width:420px;
      padding:32px 24px;
      text-align:center;
    }
    .title{
      font-size:22px;
      font-weight:600;
      margin-bottom:8px;
    }
    .subtitle{
      font-size:14px;
      color:var(--gray);
      margin-bottom:40px;
    }/* Envelope */
.envelope{
  width:260px;
  height:170px;
  margin:0 auto 28px;
  position:relative;
  cursor:pointer;
}
.env-body{
  position:absolute;
  inset:0;
  border:2px solid var(--black);
  background:var(--white);
}
.env-flap{
  position:absolute;
  inset:0;
  background:var(--red);
  clip-path: polygon(0 0, 100% 0, 50% 55%);
  transform-origin:50% 0%;
  transition: transform .7s ease;
}
.seal{
  position:absolute;
  left:50%;
  top:60%;
  transform:translate(-50%,-50%);
  width:34px;
  height:34px;
  border-radius:50%;
  background:var(--black);
  color:var(--white);
  display:flex;
  align-items:center;
  justify-content:center;
  font-size:14px;
  font-weight:600;
}

/* Letter */
.letter{
  position:absolute;
  inset:12px;
  background:var(--white);
  border:1px solid var(--black);
  padding:18px 16px;
  text-align:left;
  opacity:0;
  transform:translateY(20px);
  transition:opacity .6s ease, transform .6s ease;
  overflow:auto;
}
.letter h2{
  margin:0 0 12px;
  font-size:18px;
  font-weight:600;
  color:var(--red);
}
.letter p{
  margin:0 0 12px;
  line-height:1.6;
  font-size:15px;
}
.signature{
  margin-top:16px;
  font-style:italic;
  font-size:14px;
  color:var(--gray);
}

/* Open state */
.open .env-flap{ transform:rotateX(180deg); }
.open .letter{
  opacity:1;
  transform:translateY(0);
}

.hint{
  font-size:13px;
  color:var(--gray);
}
footer{
  margin-top:32px;
  font-size:11px;
  color:var(--gray);
}

  </style>
</head>
<body>
  <div class="container">
    <div class="title">Un message pour toi</div>
    <div class="subtitle">Appuie sur l’enveloppe</div><div class="envelope" id="envelope">
  <div class="env-body"></div>
  <div class="env-flap"></div>
  <div class="seal">❤</div>
  <div class="letter">
    <h2>Mimi,</h2>
    <p>
      Ce message est juste là pour te rappeler une chose simple :
      tu comptes énormément.
    </p>
    <p>
      Tu es une personne forte, précieuse et unique.
      Même dans les moments difficiles, tu restes quelqu’un de profondément beau.
    </p>
    <p>
      Prends soin de toi, vraiment.
      Tu mérites la douceur, le repos et tout ce qu’il y a de meilleur.
    </p>
    <div class="signature">— Quelqu’un qui t’aime beaucoup</div>
  </div>
</div>

<div class="hint">(touche à nouveau pour fermer)</div>
<footer>fait avec le cœur</footer>

  </div>  <script>
    const env = document.getElementById('envelope');
    env.addEventListener('click', () => {
      env.classList.toggle('open');
    });
  </script></body>
</html>
