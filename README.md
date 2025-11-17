<!doctype html>
<html lang="sv">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Lindsdals Bilvård – Bilservice & Rekond</title>
  <style>
    * { box-sizing: border-box; margin: 0; padding: 0; }
    body { font-family: system-ui, sans-serif; line-height: 1.6; color: #222; }
    header { background: #0a3a5f; color: #fff; padding: 1.5rem; }
    header h1 { font-size: 2rem; margin-bottom: .5rem; }
    nav a { color: #fff; margin-right: 1rem; text-decoration: none; font-weight: 600; }

    .hero {
      background: url('https://images.unsplash.com/photo-1503376780353-7e6692767b70?auto=format&fit=crop&w=1600&q=80') center/cover;
      height: 40vh;
      display: flex;
      align-items: flex-start;
      justify-content: flex-start;
      text-align: left;
      color: #fff;
      padding: 3rem 2rem 1rem 2rem;
    }
    .hero h2 { font-size: 2.5rem; text-shadow: 0 0 8px #000; }

    section { padding: 2rem 1.5rem; max-width: 900px; margin: auto; }
    h2 { margin-bottom: 1rem; color: #0a3a5f; }
    .services { display: grid; gap: 1.5rem; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); }
    .service-box {
      background: #f5f8fa;
      padding: 1.5rem;
      border-radius: 12px;
      box-shadow: 0 3px 6px rgba(0,0,0,.1);
    }
    .service-box h3 { margin-bottom: .5rem; }

    footer {
      background: #0a3a5f;
      color: #fff;
      padding: 1.5rem;
      text-align: center;
      margin-top: 2rem;
    }
      /* Responsiv meny */
    .menu-toggle { display:none; cursor:pointer; font-size:1.8rem; }
    @media (max-width:700px){
      nav { display:none; flex-direction:column; background:#0a3a5f; padding:1rem; }
      nav a { margin:0.5rem 0; }
      .menu-toggle { display:block; color:#fff; }
      nav.active { display:flex; }
    }
    /* Enkel fade-in animation */
    .fade { opacity:0; transform:translateY(20px); transition:all .6s ease; }
    .fade.visible { opacity:1; transform:translateY(0); }
</style>
</head>
<body>
  <script>
    document.addEventListener('DOMContentLoaded', () => {
      const toggle = document.getElementById('menuToggle');
      const nav = document.querySelector('nav');
      toggle.addEventListener('click', ()=> nav.classList.toggle('active'));

      const fades = document.querySelectorAll('.fade');
      const observer = new IntersectionObserver(entries => {
        entries.forEach(e => { if(e.isIntersecting) e.target.classList.add('visible'); });
      }, { threshold:0.2 });
      fades.forEach(el => observer.observe(el));
    });
  </script>
  <header>
    <span id="menuToggle" class="menu-toggle">☰</span>
    <h1>Lindsdals Bilvård</h1>
    <nav>
      <a href="#om">Om oss</a>
      <a href="#tjanster">Tjänster</a>
      <a href="#kontakt">Kontakt</a>
    </nav>
  </header>

  <div class="hero">
    <h2>Professionell bilservice & bilvård i Lindsdal</h2>
  </div>

  <section id="om">
    <h2>Om oss</h2>
    <p>
      Lindsdals Bilvård erbjuder professionell bilservice, rekond och underhåll för alla bilmodeller. 
      Vi brinner för kvalitet och noggrannhet – varje bil behandlas som om den vore vår egen.
    </p>
  </section>

  <section id="priser" class="fade">
    <h2>Prislista</h2>
    <ul>
      <li><strong>Bas-service:</strong> 1 495 kr</li>
      <li><strong>Fullständig rekond:</strong> 2 495 kr</li>
      <li><strong>Däckbyte:</strong> 395 kr</li>
      <li><strong>Diagnos & felsökning:</strong> 895 kr</li>
    </ul>
  </section>

  <section id="boka" class="fade">
    <h2>Boka tid</h2>
    <form>
      <label>Namn:<br><input type="text" required></label><br><br>
      <label>Email:<br><input type="email" required></label><br><br>
      <label>Vilken tjänst?<br>
        <select required>
          <option>Bas-service</option>
          <option>Fullständig rekond</option>
          <option>Däckservice</option>
          <option>Felsökning</option>
        </select>
      </label><br><br>
      <label>Meddelande:<br><textarea rows="4"></textarea></label><br><br>
      <button type="submit">Skicka bokning</button>
    </form>
  </section>

  <section id="tjanster" class="fade">
    <h2>Våra tjänster</h2>
    <div class="services">
      <div class="service-box">
        <h3>Bas-service</h3>
        <p>Oljebyte, filterkontroll och säkerhetsgenomgång. Perfekt för regelbundet underhåll.</p>
      </div>

      <div class="service-box">
        <h3>Fullständig rekond</h3>
        <p>Invändig och utvändig rengöring, lackskydd, dammsugning och fälgrengöring.</p>
      </div>

      <div class="service-box">
        <h3>Däckservice</h3>
        <p>Däckbyte, balansering och förvaring under säsong.</p>
      </div>

      <div class="service-box">
        <h3>Felsökning & diagnos</h3>
        <p>Avancerad felsökning och åtgärder med modern utrustning.</p>
      </div>
    </div>
  </section>

  <section id="kontakt">
    <h2>Kontakta oss</h2>
    <p>Har du frågor eller vill boka tid? Hör av dig!</p>
    <p><strong>Email:</strong> info@lindsdalsbilvard.se</p>
    <p><strong>Telefon:</strong> 070-123 45 67</p>
    <p><strong>Adress:</strong> Lindsdal, Kalmar</p>
  </section>

  <footer>
    © 2025 Lindsdals Bilvård – Alla rättigheter reserverade
  </footer>
</body>
</html>

