# pizzeriaweb
progetto di gruppo A B C 
ogni sviluppatore deve aggiungere due portate nel propio menù :
-sviluppatore a: assegnato al menù pizze
-sviluppatore b:assegnato al menù dolci
-sviluppatore c:assegnato al menù bevande
<!DOCTYPE html>
<html lang="it">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="theme-color" content="#171713">
  <meta name="description" content="L'Arte della Pizza: pizze artigianali, ingredienti selezionati e tutta la passione della tradizione italiana.">
  <title>L'Arte della Pizza | La passione in ogni fetta</title>

  <style>
    :root {
      --dark: #171713;
      --cream: #f8f1e6;
      --red: #c74630;
      --gold: #e9b66e;
      --text: #382a20;
    }

    * { box-sizing: border-box; margin: 0; padding: 0; }

    html { scroll-behavior: smooth; }

    body {
      font-family: Georgia, "Times New Roman", serif;
      background: var(--cream);
      color: var(--text);
      line-height: 1.6;
    }

    a { color: inherit; text-decoration: none; }

    .navbar {
      background: var(--dark);
      color: white;
      min-height: 82px;
      padding: 18px 7%;
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 20px;
      position: sticky;
      top: 0;
      z-index: 10;
      border-bottom: 2px solid var(--gold);
    }

    .logo {
      color: var(--gold);
      font-size: 1.25rem;
      font-weight: bold;
      letter-spacing: 1px;
    }

    .logo small {
      display: block;
      color: #eee0ca;
      font-size: .65rem;
      letter-spacing: 3px;
      text-align: center;
    }

    nav { display: flex; gap: 24px; align-items: center; }
    nav a { font-size: .95rem; }
    nav a:hover { color: var(--gold); }

    .button {
      display: inline-block;
      background: var(--red);
      color: white;
      padding: 13px 23px;
      border-radius: 4px;
      font-family: Arial, sans-serif;
      font-weight: bold;
      transition: .2s;
      border: 0;
      cursor: pointer;
    }

    .button:hover {
      background: #a93423;
      transform: translateY(-2px);
    }

    .hero {
      min-height: 590px;
      display: flex;
      align-items: center;
      padding: 80px 9%;
      color: white;
      background:
        linear-gradient(90deg, rgba(15,15,12,.94), rgba(15,15,12,.45)),
        url("https://images.unsplash.com/photo-1579751626657-72bc17010498?auto=format&fit=crop&w=2000&q=85")
        center/cover;
    }

    .hero-content { max-width: 670px; }

    .eyebrow {
      color: var(--gold);
      text-transform: uppercase;
      letter-spacing: 4px;
      font: bold .78rem Arial, sans-serif;
    }

    h1 {
      font-size: clamp(2.8rem, 6vw, 5.4rem);
      line-height: 1.05;
      margin: 22px 0;
    }

    h1 span { color: var(--gold); }

    .hero p {
      max-width: 510px;
      font: 1.05rem/1.8 Arial, sans-serif;
      color: #eee5d8;
      margin-bottom: 28px;
    }

    section { padding: 85px 8%; scroll-margin-top: 75px; }

    .section-heading {
      text-align: center;
      max-width: 650px;
      margin: 0 auto 45px;
    }

    .section-heading h2 {
      font-size: clamp(2rem, 4vw, 3.2rem);
      margin: 8px 0;
    }

    .section-heading p { color: #76695d; }

    .specials {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 26px;
    }

    .pizza-card {
      background: white;
      border-radius: 8px;
      overflow: hidden;
      box-shadow: 0 5px 24px #382a2010;
      transition: transform .25s;
    }

    .pizza-card:hover { transform: translateY(-6px); }

    .pizza-card img {
      width: 100%;
      height: 230px;
      object-fit: cover;
      display: block;
    }

    .pizza-info { padding: 22px; }

    .pizza-info h3 { font-size: 1.45rem; }

    .pizza-info p {
      color: #76695d;
      margin: 8px 0 15px;
      font: .9rem/1.6 Arial, sans-serif;
    }

    .price { color: var(--red); font-size: 1.35rem; font-weight: bold; }

    .about {
      background: var(--dark);
      color: white;
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 55px;
      align-items: center;
    }

    .about img {
      width: 100%;
      max-height: 450px;
      object-fit: cover;
      border-radius: 6px;
    }

    .about h2 { font-size: clamp(2rem, 4vw, 3.2rem); margin: 12px 0 20px; }
    .about p { color: #d6cec1; margin-bottom: 18px; }

    .contact { text-align: center; }

    .contact-grid {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 25px;
      margin: 35px 0;
    }

    .contact-item {
      background: white;
      padding: 28px 15px;
      border-radius: 6px;
    }

    .contact-item .symbol { font-size: 1.8rem; }
    .contact-item h3 { margin: 8px 0; }
    .contact-item p { color: #76695d; font: .95rem/1.6 Arial, sans-serif; }

    footer {
      background: var(--dark);
      color: #d6cec1;
      padding: 30px 7%;
      text-align: center;
      font: .85rem/1.8 Arial, sans-serif;
    }

    footer strong { color: var(--gold); }

    @media (max-width: 760px) {
      .navbar { flex-wrap: wrap; padding: 15px 5%; }
      nav { width: 100%; justify-content: center; gap: 17px; flex-wrap: wrap; }
      nav a { font-size: .85rem; }
      .hero { min-height: 520px; padding: 65px 7%; }
      section { padding: 65px 6%; }
      .specials { grid-template-columns: 1fr; }
      .pizza-card img { height: 250px; }
      .about { grid-template-columns: 1fr; gap: 30px; }
      .contact-grid { grid-template-columns: 1fr; }
    }
  </style>
</head>

<body>
  <header class="navbar">
    <a class="logo" href="#home">
      L'ARTE DELLA PIZZA
      <small>PASSIONE ITALIANA</small>
    </a>

    <nav aria-label="Navigazione principale">
      <a href="#home">Home</a>
      <a href="#menu">Il menu</a>
      <a href="#storia">La nostra storia</a>
      <a href="#contatti">Contatti</a>
    </nav>
  </header>

  <main>
    <section class="hero" id="home">
      <div class="hero-content">
        <span class="eyebrow">Tradizione e gusto</span>
        <h1>La pizza è un'arte.<br><span>La nostra passione.</span></h1>
        <p>
          Impasti preparati con cura, ingredienti selezionati
          e il profumo irresistibile della pizza appena sfornata.
          Vieni a scoprire il gusto della tradizione.
        </p>
        <a href="#menu" class="button">SCOPRI IL NOSTRO MENU</a>
      </div>
    </section>

    <section id="menu">
      <div class="section-heading">
        <span class="eyebrow">Fatte con amore</span>
        <h2>Le nostre specialità</h2>
        <p>Ogni pizza racconta una storia di sapori, tradizione e passione.</p>
      </div>

      <div class="specials">
        <article class="pizza-card">
          <img src="https://images.unsplash.com/photo-1604382355076-af4b0eb60143?auto=format&fit=crop&w=900&q=80"
               alt="Pizza Margherita con mozzarella e basilico" loading="lazy">
          <div class="pizza-info">
            <h3>Margherita</h3>
            <p>Pomodoro, mozzarella fior di latte e basilico fresco.</p>
            <span class="price">€ 6,50</span>
          </div>
        </article>

        <article class="pizza-card">
          <img src="https://images.unsplash.com/photo-1628840042765-356cda07504e?auto=format&fit=crop&w=900&q=80"
               alt="Pizza artigianale appena sfornata" loading="lazy">
          <div class="pizza-info">
            <h3>Diavola</h3>
            <p>Pomodoro, mozzarella e salame piccante.</p>
            <span class="price">€ 8,50</span>
          </div>
        </article>

        <article class="pizza-card">
          <img src="https://images.unsplash.com/photo-1571407970349-bc81e7e96d47?auto=format&fit=crop&w=900&q=80"
               alt="Pizza artigianale con ingredienti freschi" loading="lazy">
          <div class="pizza-info">
            <h3>La Speciale</h3>
            <p>Pomodoro, mozzarella, funghi e prosciutto cotto.</p>
            <span class="price">€ 9,00</span>
          </div>
        </article>
      </div>
    </section>

    <section class="about" id="storia">
      <div>
        <span class="eyebrow">La nostra filosofia</span>
        <h2>Non facciamo solo pizze. Creiamo emozioni.</h2>
        <p>
          Per noi la pizza è molto più di un piatto: è convivialità,
          famiglia e il piacere di stare insieme.
        </p>
        <p>
          Scegliamo con attenzione gli ingredienti e curiamo ogni
          dettaglio per portare sulla tua tavola una pizza ricca
          di sapore e fatta con passione.
        </p>
        <a href="#contatti" class="button">VIENI A TROVARCI</a>
      </div>

      <img
        src="https://images.unsplash.com/photo-1579751626657-72bc17010498?auto=format&fit=crop&w=1000&q=85"
        alt="Preparazione artigianale della pizza" loading="lazy">
    </section>

    <section class="contact" id="contatti">
      <div class="section-heading">
        <span class="eyebrow">Ti aspettiamo</span>
        <h2>Vieni a trovarci</h2>
        <p>La tua prossima pizza preferita ti aspetta!</p>
      </div>

      <div class="contact-grid">
        <div class="contact-item">
          <div class="symbol">📍</div>
          <h3>Dove siamo</h3>
          <p>Inserisci qui il tuo indirizzo</p>
        </div>

        <div class="contact-item">
          <div class="symbol">🕒</div>
          <h3>Orari</h3>
          <p>Inserisci qui i tuoi orari di apertura</p>
        </div>

        <div class="contact-item">
          <div class="symbol">📞</div>
          <h3>Telefono</h3>
          <p>Inserisci qui il tuo numero</p>
        </div>
      </div>

      <!-- Sostituisci il numero con quello della pizzeria -->
      <a class="button" href="tel:+390000000000">
        CHIAMACI PER ORDINARE
      </a>
    </section>
  </main>

  <footer>
    <p><strong>L'Arte della Pizza</strong> · La passione in ogni fetta.</p>
    <p>© <span id="year"></span> L'Arte della Pizza · Tutti i diritti riservati.</p>
  </footer>
