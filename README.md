# KRISKA-STORE<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>KRISKA STORE – Tu estilo, tu historia</title>
  <!--
  ✨ Cómo editar rápido (busca estas secciones):
  1) ⚙️ CONFIGURACIÓN: cambia colores, nombre, WhatsApp, redes.
  2) 🧷 NAV / HERO: textos superiores.
  3) 🛍️ PRODUCTOS: duplica una tarjeta y edita imagen, precio y categoría.
  4) 🧰 CATEGORÍAS: añade o quita botones (deben coincidir con data-category).
  5) 📦 ENLACES: reemplaza # por tus URLs.
  -->
  <style>
    /* =====================
       ⚙️ CONFIGURACIÓN RÁPIDA
       Cambia estos colores y fuentes
       ===================== */
    :root{
      --brand:#111111;        /* Fondo principal */
      --panel:#18181b;        /* Tarjetas/fondos */
      --text:#fafafa;         /* Texto claro */
      --muted:#a1a1aa;        /* Texto secundario */
      --accent:#ff00c8;       /* Botones / acento (magenta KRISKA) */
      --accent-2:#ff7adf;     /* Acento suave (hover) */
      --chip:#2a2a30;         /* Chips de categoría */
      --success:#22c55e;      /* Etiquetas de descuento */
      --danger:#ef4444;       /* Etiquetas de oferta */
      --radius:18px;          /* Bordes redondeados */
      --font-system: ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial, "Apple Color Emoji","Segoe UI Emoji";
    }

    *{box-sizing:border-box}
    html,body{margin:0;height:100%;scroll-behavior:smooth}
    body{
      font-family:var(--font-system);
      color:var(--text);
      background:linear-gradient(180deg, #0c0c0f 0%, var(--brand) 100%);
    }

    /* Layout */
    .container{max-width:1080px;margin-inline:auto;padding:24px}
    header{position:sticky;top:0;z-index:50;background:rgba(12,12,15,.7);backdrop-filter:blur(8px);border-bottom:1px solid #26262b}
    .nav{display:flex;align-items:center;gap:16px;justify-content:space-between;padding:14px 0}
    .logo{display:flex;align-items:center;gap:12px}
    .logo-mark{width:40px;height:40px;border-radius:50%;display:grid;place-items:center;background:radial-gradient(60% 60% at 50% 35%, var(--accent), transparent 60%),#1a1a1d;border:1px solid #2a2a30;box-shadow:0 0 0 3px #111 inset}
    .brand{font-weight:800;letter-spacing:.5px}
    .tag{color:var(--muted);font-size:.9rem}

    .cta{display:inline-block;background:var(--accent);color:#111;padding:10px 16px;border-radius:999px;font-weight:700;text-decoration:none;transition:transform .1s ease, background .2s}
    .cta:hover{background:var(--accent-2);transform:translateY(-1px)}

    /* Hero */
    .hero{padding:56px 0 24px;display:grid;gap:20px;align-items:center}
    .hero-card{background:linear-gradient(180deg,#1d1d22 0%,#141418 100%);border:1px solid #2a2a30;border-radius:var(--radius);padding:28px;display:grid;gap:12px;box-shadow:0 10px 30px rgba(0,0,0,.25)}
    .hero h1{margin:0;font-size:clamp(24px,4vw,40px)}
    .hero p{margin:0;color:var(--muted)}

    /* Categorías */
    .chips{display:flex;flex-wrap:wrap;gap:10px;margin:6px 0 2px}
    .chip{background:var(--chip);border:1px solid #2e2e36;color:#eaeaea;padding:8px 14px;border-radius:999px;cursor:pointer;font-weight:600}
    .chip[data-active="true"]{background:var(--accent);color:#141414;border-color:transparent}

    /* Grid productos */
    .grid{display:grid;gap:16px;margin-top:18px;grid-template-columns:repeat(auto-fill,minmax(240px,1fr))}
    .card{background:var(--panel);border:1px solid #2a2a30;border-radius:var(--radius);overflow:hidden;display:flex;flex-direction:column;min-height:100%}
    .img-wrap{aspect-ratio:4/5;background:#0f0f12;display:grid;place-items:center;position:relative}
    .img-wrap img{width:100%;height:100%;object-fit:cover}
    .badge{position:absolute;top:10px;left:10px;background:var(--success);color:#06240f;font-weight:800;padding:6px 10px;border-radius:999px;font-size:.8rem}
    .content{padding:14px 14px 18px;display:grid;gap:8px}
    .title{font-weight:800}
    .price{display:flex;align-items:center;gap:10px}
    .old{color:var(--muted);text-decoration:line-through}
    .buy{margin-top:6px;display:flex;gap:8px}
    .btn{flex:1;display:inline-flex;justify-content:center;align-items:center;gap:8px;padding:10px 12px;border-radius:12px;border:1px solid #2a2a30;background:#0f0f12;color:#f5f5f5;cursor:pointer;font-weight:700;text-decoration:none}
    .btn.primary{background:var(--accent);color:#111;border-color:transparent}
    .btn.primary:hover{background:var(--accent-2)}

    /* Secciones informativas */
    .section{margin-top:36px}
    .section .card{padding:20px}

    /* Footer */
    footer{margin-top:40px;border-top:1px solid #2a2a30;color:var(--muted)}
    footer a{color:#eaeaea}

    /* Responsivo */
    @media (min-width:900px){
      .hero{grid-template-columns:1.2fr .8fr}
    }
  </style>
</head>
<body>
  <header>
    <div class="container nav">
      <div class="logo">
        <!-- Reemplaza el SVG por tu logotipo si quieres -->
        <div class="logo-mark" aria-hidden="true">
          <svg width="22" height="22" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M6 19c4-2 8-2 12 0M7 8c.7-2.2 2.3-3.5 5-3.5S16.3 5.8 17 8m2 4a7 7 0 1 1-14 0 7 7 0 0 1 14 0Z" stroke="#fff" stroke-width="1.4"/>
          </svg>
        </div>
        <div>
          <div class="brand">KRISKA STORE</div>
          <div class="tag">Tu estilo, tu historia</div>
        </div>
      </div>
      <nav style="display:flex;gap:10px;align-items:center">
        <a class="cta" id="whatsappTop" href="https://wa.me/573000000000?text=Hola%20KRISKA%20STORE%2C%20quiero%20comprar" target="_blank" rel="noopener">WhatsApp</a>
      </nav>
    </div>
  </header>

  <main class="container">
    <!-- 🧷 HERO ============================= -->
    <section class="hero">
      <div class="hero-card">
        <h1>Descubre moda femenina con actitud</h1>
        <p>Prendas juveniles, sofisticadas y delicadas para crear tu historia con estilo.</p>
        <div style="display:flex;gap:10px;margin-top:8px">
          <a class="cta" href="#catalogo">Ver catálogo</a>
          <a class="btn" href="#sobre">Sobre la marca</a>
        </div>
        <div class="chips" id="chips">
          <!-- 🧰 CATEGORÍAS: añade/quita; deben coincidir con data-category -->
          <button class="chip" data-filter="all" data-active="true">Todas</button>
          <button class="chip" data-filter="Casual">Casual</button>
          <button class="chip" data-filter="Fiesta">Fiesta</button>
          <button class="chip" data-filter="Oficina">Oficina</button>
          <button class="chip" data-filter="Abrigos">Abrigos</button>
        </div>
      </div>
      <div class="hero-card" style="background:radial-gradient(120% 140% at 80% 0%, rgba(255,0,200,.25) 0%, transparent 50%), #17171c">
        <img alt="Modelo KRISKA" src="https://images.unsplash.com/photo-1542060748-10c28b62716f?q=80&w=1200&auto=format&fit=crop" style="width:100%;border-radius:calc(var(--radius) - 6px);border:1px solid #2a2a30;object-fit:cover"/>
      </div>
    </section>

    <!-- 🛍️ CATÁLOGO ========================= -->
    <section id="catalogo" class="section">
      <h2 style="margin:0 0 10px">Catálogo</h2>
      <div class="grid" id="grid">
        <!-- 🔁 PRODUCTO (duplica esta tarjeta para añadir más) -->
        <article class="card" data-category="Casual,Abrigos">
          <div class="img-wrap">
            <span class="badge">-14%</span>
            <img src="https://images.unsplash.com/photo-1520975922203-bf73b1b6aeae?q=80&w=1000&auto=format&fit=crop" alt="Chaqueta tipo envejecida marrón"/>
          </div>
          <div class="content">
            <div class="title">Chaqueta tipo envejecida</div>
            <div class="price"><strong>$95.000</strong> <span class="old">$110.000</span></div>
            <div class="buy">
              <a class="btn primary" href="https://wa.me/573000000000?text=Hola%2C%20quiero%20la%20Chaqueta%20tipo%20envejecida" target="_blank" rel="noopener">Comprar</a>
              <a class="btn" href="#">Agregar a carrito</a>
            </div>
          </div>
        </article>

        <article class="card" data-category="Casual,Oficina">
          <div class="img-wrap">
            <span class="badge" style="background:var(--danger);color:#2a0909">-9%</span>
            <img src="https://images.unsplash.com/photo-1486430721640-899b4a7bbdb8?q=80&w=1000&auto=format&fit=crop" alt="Chaqueta crop azul cielo"/>
          </div>
          <div class="content">
            <div class="title">Chaqueta Crop Azul Cielo</div>
            <div class="price"><strong>$100.000</strong> <span class="old">$110.000</span></div>
            <div class="buy">
              <a class="btn primary" href="https://wa.me/573000000000?text=Hola%2C%20quiero%20la%20Chaqueta%20Crop%20Azul%20Cielo" target="_blank" rel="noopener">Comprar</a>
              <a class="btn" href="#">Agregar a carrito</a>
            </div>
          </div>
        </article>

        <article class="card" data-category="Abrigos,Fiesta">
          <div class="img-wrap">
            <img src="https://images.unsplash.com/photo-1548883354-2b06321bdbe9?q=80&w=1000&auto=format&fit=crop" alt="Chaqueta Winter Glow blanca"/>
          </div>
          <div class="content">
            <div class="title">Chaqueta Winter Glow ✨</div>
            <div class="price"><strong>$100.000</strong> <span class="old">$118.000</span></div>
            <div class="buy">
              <a class="btn primary" href="https://wa.me/573000000000?text=Hola%2C%20quiero%20la%20Chaqueta%20Winter%20Glow" target="_blank" rel="noopener">Comprar</a>
              <a class="btn" href="#">Agregar a carrito</a>
            </div>
          </div>
        </article>

        <article class="card" data-category="Casual,Oficina">
          <div class="img-wrap">
            <img src="https://images.unsplash.com/photo-1489533119213-66a5cd877091?q=80&w=1000&auto=format&fit=crop" alt="Chaqueta ovejero negra con beige"/>
          </div>
          <div class="content">
            <div class="title">Chaqueta Ovejero</div>
            <div class="price"><strong>$129.999</strong> <span class="old">$140.000</span></div>
            <div class="buy">
              <a class="btn primary" href="https://wa.me/573000000000?text=Hola%2C%20quiero%20la%20Chaqueta%20Ovejero" target="_blank" rel="noopener">Comprar</a>
              <a class="btn" href="#">Agregar a carrito</a>
            </div>
          </div>
        </article>
      </div>
    </section>

    <!-- 🪪 SOBRE LA MARCA =================== -->
    <section id="sobre" class="section">
      <div class="card">
        <h2 style="margin:0 0 6px">Sobre KRISKA STORE</h2>
        <p style="margin:0;color:var(--muted)">Moda femenina juvenil, sofisticada y delicada. Enviamos a toda Colombia. Pagos seguros y asesoría por WhatsApp.</p>
      </div>
    </section>

    <!-- ☎️ CONTACTO ======================== -->
    <section class="section">
      <div class="card" style="display:grid;gap:10px">
        <h2 style="margin:0">Contáctanos</h2>
        <div style="display:flex;flex-wrap:wrap;gap:10px">
          <a class="btn primary" href="https://wa.me/573000000000?text=Hola%20KRISKA%20STORE" target="_blank" rel="noopener">Escríbenos por WhatsApp</a>
          <a class="btn" href="#">Instagram</a>
          <a class="btn" href="#">Facebook</a>
          <a class="btn" href="mailto:ventas@kriskastore.com">ventas@kriskastore.com</a>
        </div>
      </div>
    </section>

    <footer class="container" style="padding:22px 0 36px">
      <div style="display:flex;justify-content:space-between;gap:10px;flex-wrap:wrap">
        <small>© <span id="year"></span> KRISKA STORE. Todos los derechos reservados.</small>
        <small><a href="#">Política de privacidad</a> · <a href="#">Términos</a></small>
      </div>
    </footer>
  </main>

  <!-- JS: filtro de categorías + año dinámico -->
  <script>
    const chips = document.querySelectorAll('.chip');
    const cards = document.querySelectorAll('.card[data-category]');
    const year = document.getElementById('year');
    year.textContent = new Date().getFullYear();

    chips.forEach(chip=>{
      chip.addEventListener('click', ()=>{
        chips.forEach(c=>c.dataset.active = 'false');
        chip.dataset.active = 'true';
        const filter = chip.dataset.filter;
        cards.forEach(card=>{
          const cats = card.dataset.category.split(',');
          const show = filter==='all' || cats.includes(filter);
          card.style.display = show ? 'flex' : 'none';
        });
        window.location.hash = '#catalogo';
      });
    });
  </script>
</body>
</html>
