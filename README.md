<!doctype html>
<html lang="id">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>Typing Banner — Enhanced</title>
<style>
  :root{
    --bg1:#0f172a;
    --bg2:#071428;
    --card-grad-1: #0ea5a4; /* teal */
    --card-grad-2: #7c3aed; /* purple */
    --glass: rgba(255,255,255,0.06);
    --glass-2: rgba(255,255,255,0.04);
  }

  /* Page */
  body{
    margin:0;
    min-height:100vh;
    display:grid;
    place-items:center;
    background: radial-gradient(1200px 600px at 10% 10%, rgba(124,58,237,0.12), transparent 8%),
                radial-gradient(1000px 500px at 90% 90%, rgba(14,165,164,0.08), transparent 8%),
                linear-gradient(135deg,var(--bg1), var(--bg2));
    font-family: Inter, "Segoe UI", Roboto, "Fira Code", monospace;
    -webkit-font-smoothing:antialiased;
    color: #e6eef6;
  }

  /* Card container */
  .card{
    width: min(920px, 92vw);
    border-radius: 20px;
    padding: 28px;
    display:flex;
    gap:24px;
    align-items:center;
    background: linear-gradient(180deg,var(--glass), var(--glass-2));
    backdrop-filter: blur(8px) saturate(1.1);
    box-shadow:
      0 10px 30px rgba(2,6,23,0.6),
      0 2px 6px rgba(124,58,237,0.08),
      inset 0 1px 0 rgba(255,255,255,0.02);
    border: 1px solid rgba(255,255,255,0.06);
    position:relative;
    overflow: hidden;
  }

  /* Decorative gradient stripe */
  .card::before{
    content:"";
    position:absolute;
    left:-30%;
    top:-40%;
    width:160%;
    height:120%;
    background: conic-gradient(from 180deg at 50% 50%, rgba(124,58,237,0.18), rgba(14,165,164,0.14), transparent 40%);
    transform: rotate(12deg);
    filter: blur(40px) saturate(1.3);
    pointer-events:none;
  }

  .avatar{
    width:96px;
    height:96px;
    border-radius:50%;
    flex: 0 0 auto;
    display:grid;
    place-items:center;
    background: linear-gradient(135deg,var(--card-grad-1), var(--card-grad-2));
    box-shadow: 0 6px 18px rgba(105,50,255,0.18);
    border: 3px solid rgba(255,255,255,0.06);
    overflow:hidden;
    position:relative;
  }
  .avatar img{ width:100%; height:100%; object-fit:cover; display:block; }

  /* Text area */
  .content{
    flex:1 1 auto;
    min-width:0;
  }

  .headline{
    margin:0 0 6px 0;
    font-weight:700;
    font-size:20px;
    letter-spacing:0.6px;
    color: #e9fbff;
    display:flex;
    align-items:center;
    gap:10px;
  }
  .sub{
    margin:0 0 14px 0;
    color: rgba(230,238,246,0.78);
    font-size:13px;
  }

  /* Typing image wrapper */
  .type-wrap{
    display:flex;
    align-items:center;
    gap:14px;
  }

  .typing-bubble{
    background: linear-gradient(90deg, rgba(255,255,255,0.03), rgba(255,255,255,0.02));
    padding: 14px 18px;
    border-radius: 14px;
    border: 1px solid rgba(255,255,255,0.04);
    box-shadow: 0 6px 20px rgba(2,6,23,0.45);
    display:inline-block;
  }

  /* make the image responsive */
  .typing-bubble img{
    display:block;
    max-width:100%;
    height:auto;
    width:600px;
    border-radius:8px;
  }

  /* small caption with hint */
  .hint{
    margin-top:10px;
    font-size:12px;
    color: rgba(230,238,246,0.6);
  }

  /* Responsive tweaks */
  @media (max-width:720px){
    .card{ padding:18px; gap:12px; flex-direction:column; align-items:flex-start; border-radius:14px; }
    .avatar{ width:72px; height:72px; }
    .typing-bubble img{ width:100%; }
    .headline{ font-size:18px; }
  }
</style>
</head>
<body>
  <main class="card" role="region" aria-label="Animated typing banner">
    <div class="avatar" title="Logo / Avatar (optional)">
      <!-- put your avatar here or leave gradient -->
      <!-- <img src="avatar.jpg" alt="Avatar"> -->
      <svg width="64" height="64" viewBox="0 0 24 24" fill="none" aria-hidden>
        <circle cx="12" cy="8" r="3.2" fill="white" opacity="0.92"/>
        <path d="M4 20c0-3.3 3.6-6 8-6s8 2.7 8 6" stroke="white" stroke-opacity="0.85" stroke-width="1.4" stroke-linecap="round" stroke-linejoin="round"/>
      </svg>
    </div>

    <section class="content">
      <h1 class="headline">Start Fresh — Visual Typing Banner</h1>
      <div class="sub">Code. Create. Repeat. — Animated, modern, and easy to customize.</div>

      <div class="type-wrap">
        <div class="typing-bubble" aria-hidden="true">
          <!-- The readme-typing-svg image (customize text / color / speed in URL) -->
          <img
            src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&size=28&duration=2200&pause=600&color=00ffd5&center=true&vCenter=true&repeat=true&width=600&lines=Start+Fresh+Every+Day;Code.+Create.+Repeat."
            alt="Animated typing: Start Fresh Every Day — Code. Create. Repeat."
          />
        </div>
      </div>

      <div class="hint">Tip: ubah teks pada URL <code>&lines=...</code> atau ganti <code>&color=</code> &amp; <code>&duration=</code> untuk menyesuaikan.</div>
    </section>
  </main>
</body>
</html>
