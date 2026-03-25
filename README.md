<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ML Projects Portfolio</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Mono:wght@400;500&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  *,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
  :root{
    --black:#0a0a0a;--white:#fafaf8;--cream:#f4f1ea;
    --purple:#7c3aed;--purple-light:#ede9fe;--purple-mid:#a78bfa;
    --teal:#0d9488;--teal-light:#ccfbf1;
    --amber:#d97706;--amber-light:#fef3c7;
    --coral:#e11d48;--coral-light:#ffe4e6;
    --blue:#1d4ed8;--blue-light:#dbeafe;
    --green:#15803d;--green-light:#dcfce7;
    --gray:#6b7280;--border:#e5e2d9;
    --font-display:'Syne',sans-serif;
    --font-body:'DM Sans',sans-serif;
    --font-mono:'DM Mono',monospace;
  }
  html{scroll-behavior:smooth}
  body{background:var(--white);color:var(--black);font-family:var(--font-body);font-size:15px;line-height:1.7;-webkit-font-smoothing:antialiased}

  /* ── HERO ── */
  .hero{
    background:var(--black);color:var(--white);
    padding:80px 40px 72px;
    position:relative;overflow:hidden;
  }
  .hero::before{
    content:'';position:absolute;inset:0;
    background:radial-gradient(ellipse 80% 60% at 60% 110%,#7c3aed33,transparent),
               radial-gradient(ellipse 50% 40% at 10% 0%,#0d948822,transparent);
    pointer-events:none;
  }
  .hero-inner{max-width:860px;margin:0 auto;position:relative}
  .hero-eyebrow{
    display:inline-flex;align-items:center;gap:8px;
    font-family:var(--font-mono);font-size:11px;letter-spacing:.12em;text-transform:uppercase;
    color:#a78bfa;margin-bottom:24px;
  }
  .hero-eyebrow span{display:inline-block;width:28px;height:1px;background:#a78bfa}
  .hero h1{
    font-family:var(--font-display);font-size:clamp(42px,7vw,80px);font-weight:800;
    line-height:1.0;letter-spacing:-.03em;margin-bottom:28px;
  }
  .hero h1 em{font-style:normal;color:#a78bfa}
  .hero-desc{font-size:17px;color:#cbd5e1;max-width:540px;line-height:1.75;margin-bottom:40px}
  .hero-badges{display:flex;flex-wrap:wrap;gap:10px}
  .badge{
    font-family:var(--font-mono);font-size:11px;
    padding:6px 14px;border-radius:100px;
    border:1px solid rgba(255,255,255,.15);color:rgba(255,255,255,.7);
    letter-spacing:.06em;
  }
  .badge.purple{background:#7c3aed22;border-color:#7c3aed55;color:#c4b5fd}
  .badge.teal{background:#0d948822;border-color:#0d948855;color:#5eead4}
  .badge.amber{background:#d9770622;border-color:#d9770655;color:#fbbf24}

  /* ── GRID OVERVIEW ── */
  .section{padding:64px 40px;max-width:900px;margin:0 auto}
  .section-label{
    font-family:var(--font-mono);font-size:11px;letter-spacing:.12em;text-transform:uppercase;
    color:var(--gray);margin-bottom:32px;
    display:flex;align-items:center;gap:12px;
  }
  .section-label::after{content:'';flex:1;height:1px;background:var(--border)}

  .project-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:20px}
  @media(max-width:600px){.project-grid{grid-template-columns:1fr}}

  .project-card{
    border:1px solid var(--border);border-radius:16px;
    padding:28px;position:relative;overflow:hidden;
    transition:transform .2s,box-shadow .2s;cursor:default;
    background:var(--white);
  }
  .project-card:hover{transform:translateY(-3px);box-shadow:0 16px 40px rgba(0,0,0,.08)}
  .project-card::before{
    content:'';position:absolute;top:0;left:0;right:0;height:3px;
    border-radius:16px 16px 0 0;
  }
  .card-purple::before{background:linear-gradient(90deg,#7c3aed,#a78bfa)}
  .card-teal::before{background:linear-gradient(90deg,#0d9488,#34d399)}
  .card-coral::before{background:linear-gradient(90deg,#e11d48,#fb7185)}
  .card-blue::before{background:linear-gradient(90deg,#1d4ed8,#60a5fa)}

  .card-num{
    font-family:var(--font-mono);font-size:11px;letter-spacing:.1em;
    color:var(--gray);margin-bottom:12px;
  }
  .card-title{
    font-family:var(--font-display);font-size:20px;font-weight:700;
    line-height:1.25;margin-bottom:8px;
  }
  .card-desc{font-size:13px;color:var(--gray);line-height:1.65;margin-bottom:20px}
  .card-tags{display:flex;flex-wrap:wrap;gap:6px}
  .tag{
    font-size:11px;font-family:var(--font-mono);padding:4px 10px;
    border-radius:6px;letter-spacing:.04em;
  }
  .tag-purple{background:var(--purple-light);color:var(--purple)}
  .tag-teal{background:var(--teal-light);color:var(--teal)}
  .tag-coral{background:var(--coral-light);color:var(--coral)}
  .tag-blue{background:var(--blue-light);color:var(--blue)}
  .tag-green{background:var(--green-light);color:var(--green)}
  .tag-amber{background:var(--amber-light);color:var(--amber)}

  .card-acc{
    position:absolute;top:28px;right:24px;
    font-family:var(--font-display);font-size:28px;font-weight:800;
    opacity:.12;letter-spacing:-.02em;
  }

  /* ── DIVIDER ── */
  .divider{border:none;border-top:1px solid var(--border);margin:0 40px}

  /* ── PROJECT DETAILS ── */
  .project-detail{padding:56px 40px;max-width:900px;margin:0 auto}
  .project-detail + .project-detail{border-top:1px solid var(--border)}

  .detail-header{display:flex;align-items:flex-start;gap:20px;margin-bottom:36px}
  .detail-icon{
    width:52px;height:52px;border-radius:14px;
    display:flex;align-items:center;justify-content:center;
    font-size:24px;flex-shrink:0;
  }
  .icon-purple{background:var(--purple-light)}
  .icon-teal{background:var(--teal-light)}
  .icon-coral{background:var(--coral-light)}
  .icon-blue{background:var(--blue-light)}

  .detail-meta{}
  .detail-meta h2{font-family:var(--font-display);font-size:28px;font-weight:800;letter-spacing:-.02em;margin-bottom:4px}
  .detail-meta p{color:var(--gray);font-size:14px}

  /* stat row */
  .stat-row{display:grid;grid-template-columns:repeat(3,1fr);gap:14px;margin-bottom:32px}
  @media(max-width:600px){.stat-row{grid-template-columns:1fr 1fr}}
  .stat-box{
    background:var(--cream);border-radius:12px;padding:16px 18px;
  }
  .stat-label{font-size:11px;font-family:var(--font-mono);color:var(--gray);letter-spacing:.06em;text-transform:uppercase;margin-bottom:4px}
  .stat-val{font-family:var(--font-display);font-size:22px;font-weight:700;letter-spacing:-.02em}
  .stat-val.purple{color:var(--purple)}
  .stat-val.teal{color:var(--teal)}
  .stat-val.coral{color:var(--coral)}
  .stat-val.blue{color:var(--blue)}

  /* model leaderboard */
  .leaderboard{border:1px solid var(--border);border-radius:12px;overflow:hidden;margin-bottom:28px}
  .lb-row{
    display:flex;align-items:center;padding:12px 18px;gap:14px;
    border-bottom:1px solid var(--border);font-size:14px;
    transition:background .15s;
  }
  .lb-row:last-child{border-bottom:none}
  .lb-row:hover{background:var(--cream)}
  .lb-rank{
    font-family:var(--font-mono);font-size:12px;color:var(--gray);
    width:24px;text-align:center;flex-shrink:0;
  }
  .lb-rank.gold{color:#d97706;font-weight:700}
  .lb-rank.silver{color:#6b7280;font-weight:700}
  .lb-rank.bronze{color:#b45309;font-weight:700}
  .lb-name{flex:1;font-weight:500}
  .lb-bar-wrap{width:140px;height:6px;background:#e5e7eb;border-radius:3px;flex-shrink:0}
  .lb-bar{height:6px;border-radius:3px;background:var(--purple)}
  .lb-bar.teal{background:var(--teal)}
  .lb-bar.coral{background:var(--coral)}
  .lb-bar.blue{background:var(--blue)}
  .lb-acc{font-family:var(--font-mono);font-size:12px;font-weight:500;width:44px;text-align:right;flex-shrink:0}

  /* code block */
  .code-block{
    background:#0f172a;color:#94a3b8;
    border-radius:12px;padding:20px 22px;
    font-family:var(--font-mono);font-size:12px;line-height:1.8;
    margin-bottom:20px;overflow-x:auto;
  }
  .code-block .kw{color:#818cf8}
  .code-block .str{color:#34d399}
  .code-block .cm{color:#475569}
  .code-block .fn{color:#fb923c}
  .code-block .num{color:#f472b6}

  /* arch diagram */
  .arch{
    border:1px solid var(--border);border-radius:12px;
    padding:24px;background:var(--cream);margin-bottom:28px;
    display:flex;align-items:center;justify-content:center;gap:0;flex-wrap:wrap;
  }
  .arch-node{
    background:var(--white);border:1px solid var(--border);border-radius:10px;
    padding:10px 18px;font-size:13px;font-weight:500;white-space:nowrap;
  }
  .arch-arrow{
    font-size:18px;color:var(--gray);margin:0 6px;
  }
  .arch-node.highlight{background:var(--black);color:var(--white);border-color:var(--black)}
  .arch-node.purple-node{background:var(--purple-light);color:var(--purple);border-color:#c4b5fd}
  .arch-node.teal-node{background:var(--teal-light);color:var(--teal);border-color:#99f6e4}

  /* features table */
  .feat-grid{display:grid;grid-template-columns:1fr 1fr;gap:12px;margin-bottom:28px}
  @media(max-width:600px){.feat-grid{grid-template-columns:1fr}}
  .feat-item{
    border:1px solid var(--border);border-radius:10px;padding:14px 16px;
    display:flex;gap:12px;align-items:flex-start;
  }
  .feat-dot{width:8px;height:8px;border-radius:50%;flex-shrink:0;margin-top:6px}
  .feat-dot.purple{background:var(--purple)}
  .feat-dot.teal{background:var(--teal)}
  .feat-dot.coral{background:var(--coral)}
  .feat-dot.blue{background:var(--blue)}
  .feat-name{font-weight:600;font-size:13px;margin-bottom:2px}
  .feat-sub{font-size:12px;color:var(--gray)}

  /* ── GETTING STARTED ── */
  .get-started{
    background:var(--black);color:var(--white);
    padding:72px 40px;margin-top:0;
  }
  .gs-inner{max-width:860px;margin:0 auto}
  .gs-inner h2{font-family:var(--font-display);font-size:36px;font-weight:800;letter-spacing:-.03em;margin-bottom:8px}
  .gs-inner > p{color:#94a3b8;margin-bottom:40px;font-size:15px}
  .steps{display:grid;grid-template-columns:repeat(3,1fr);gap:20px}
  @media(max-width:640px){.steps{grid-template-columns:1fr}}
  .step{background:#18181b;border:1px solid #27272a;border-radius:14px;padding:24px}
  .step-num{
    font-family:var(--font-mono);font-size:11px;color:#a78bfa;
    letter-spacing:.1em;margin-bottom:12px;
  }
  .step h3{font-family:var(--font-display);font-size:17px;font-weight:700;margin-bottom:10px}
  .step-code{
    background:#0a0a0a;border:1px solid #27272a;border-radius:8px;
    padding:10px 14px;font-family:var(--font-mono);font-size:11px;
    color:#34d399;margin-top:12px;word-break:break-all;
  }

  /* ── FOOTER ── */
  footer{
    border-top:1px solid var(--border);
    padding:32px 40px;max-width:900px;margin:0 auto;
    display:flex;align-items:center;justify-content:space-between;
    flex-wrap:wrap;gap:12px;
  }
  footer p{font-size:13px;color:var(--gray)}
  .footer-tags{display:flex;gap:8px;flex-wrap:wrap}
</style>
</head>
<body>

<!-- ══════════ HERO ══════════ -->
<header class="hero">
  <div class="hero-inner">
    <div class="hero-eyebrow"><span></span> Machine Learning Portfolio</div>
    <h1>Four Projects.<br><em>One Vision.</em></h1>
    <p class="hero-desc">
      From handwritten digits to financial credit scoring — a deep dive into classical ML and neural networks, benchmarked and battle-tested.
    </p>
    <div class="hero-badges">
      <span class="badge purple">TensorFlow · Keras</span>
      <span class="badge teal">Scikit-Learn · XGBoost</span>
      <span class="badge amber">Python 3.12</span>
      <span class="badge">Jupyter Notebook</span>
      <span class="badge">Pandas · NumPy</span>
    </div>
  </div>
</header>

<!-- ══════════ PROJECT OVERVIEW CARDS ══════════ -->
<section class="section">
  <p class="section-label">Projects at a Glance</p>
  <div class="project-grid">

    <div class="project-card card-purple">
      <div class="card-acc">~98%</div>
      <p class="card-num">01 / Deep Learning</p>
      <h3 class="card-title">MNIST Digit Recognition</h3>
      <p class="card-desc">Dense neural network trained on 70K grayscale images to classify handwritten digits 0–9 with near-perfect accuracy.</p>
      <div class="card-tags">
        <span class="tag tag-purple">TensorFlow</span>
        <span class="tag tag-purple">Keras</span>
        <span class="tag tag-purple">Softmax</span>
      </div>
    </div>

    <div class="project-card card-teal">
      <div class="card-acc">A–Z</div>
      <p class="card-num">02 / Deep Learning</p>
      <h3 class="card-title">EMNIST Letter Recognition</h3>
      <p class="card-desc">Extended MNIST — classifies 26 handwritten English letters with early stopping and learning rate scheduling callbacks.</p>
      <div class="card-tags">
        <span class="tag tag-teal">EMNIST</span>
        <span class="tag tag-teal">EarlyStopping</span>
        <span class="tag tag-teal">Callbacks</span>
      </div>
    </div>

    <div class="project-card card-coral">
      <div class="card-acc">98.2%</div>
      <p class="card-num">03 / Classical ML</p>
      <h3 class="card-title">Breast Cancer Detection</h3>
      <p class="card-desc">7-model benchmark on 569 patient samples. SVM tops the leaderboard at 98.2% — every model, one clean comparison.</p>
      <div class="card-tags">
        <span class="tag tag-coral">SVM</span>
        <span class="tag tag-coral">Random Forest</span>
        <span class="tag tag-coral">Benchmark</span>
      </div>
    </div>

    <div class="project-card card-blue">
      <div class="card-acc">XGB</div>
      <p class="card-num">04 / Ensemble ML</p>
      <h3 class="card-title">Credit Score Classification</h3>
      <p class="card-desc">Full-pipeline financial scoring — messy real-world data, custom feature engineering, 6 models auto-benchmarked.</p>
      <div class="card-tags">
        <span class="tag tag-blue">XGBoost</span>
        <span class="tag tag-blue">Feature Eng.</span>
        <span class="tag tag-blue">RobustScaler</span>
      </div>
    </div>

  </div>
</section>

<hr class="divider">

<!-- ══════════ PROJECT 1 ══════════ -->
<section class="project-detail">
  <div class="detail-header">
    <div class="detail-icon icon-purple">🔢</div>
    <div class="detail-meta">
      <h2>MNIST Digit Recognition</h2>
      <p>Notebook: <code>MNIST.ipynb</code> · Framework: TensorFlow / Keras</p>
    </div>
  </div>

  <div class="stat-row">
    <div class="stat-box"><div class="stat-label">Training Samples</div><div class="stat-val purple">60,000</div></div>
    <div class="stat-box"><div class="stat-label">Test Samples</div><div class="stat-val purple">10,000</div></div>
    <div class="stat-box"><div class="stat-label">Classes</div><div class="stat-val purple">10 digits</div></div>
  </div>

  <p style="margin-bottom:16px;font-size:14px;color:var(--gray)">Network Architecture</p>
  <div class="arch" style="margin-bottom:28px">
    <div class="arch-node">Input 28×28</div>
    <div class="arch-arrow">→</div>
    <div class="arch-node purple-node">Flatten</div>
    <div class="arch-arrow">→</div>
    <div class="arch-node highlight">Dense 128 ReLU</div>
    <div class="arch-arrow">→</div>
    <div class="arch-node purple-node">Dense 10 Softmax</div>
    <div class="arch-arrow">→</div>
    <div class="arch-node">Output</div>
  </div>

  <div class="code-block">
<span class="cm"># Normalize + one-hot encode</span>
x_train = x_train / <span class="num">255</span>
y_train = <span class="fn">to_categorical</span>(y_train, <span class="num">10</span>)

model = <span class="fn">Sequential</span>([
    <span class="fn">Input</span>(shape=(<span class="num">28</span>, <span class="num">28</span>)),
    <span class="fn">Flatten</span>(),
    <span class="fn">Dense</span>(<span class="num">128</span>, activation=<span class="str">'relu'</span>),
    <span class="fn">Dense</span>(<span class="num">10</span>,  activation=<span class="str">'softmax'</span>),
])
model.<span class="fn">compile</span>(optimizer=<span class="str">'adam'</span>, loss=<span class="str">'categorical_crossentropy'</span>, metrics=[<span class="str">'accuracy'</span>])
model.<span class="fn">fit</span>(x_train, y_train, epochs=<span class="num">5</span>, batch_size=<span class="num">32</span>)
  </div>
</section>

<hr class="divider">

<!-- ══════════ PROJECT 2 ══════════ -->
<section class="project-detail">
  <div class="detail-header">
    <div class="detail-icon icon-teal">🔤</div>
    <div class="detail-meta">
      <h2>EMNIST Letter Recognition</h2>
      <p>Notebook: <code>EMNIST.ipynb</code> · Dataset: EMNIST Letters CSV</p>
    </div>
  </div>

  <div class="stat-row">
    <div class="stat-box"><div class="stat-label">Classes</div><div class="stat-val teal">26 letters</div></div>
    <div class="stat-box"><div class="stat-label">Image Size</div><div class="stat-val teal">28 × 28</div></div>
    <div class="stat-box"><div class="stat-label">Val Split</div><div class="stat-val teal">20%</div></div>
  </div>

  <p style="margin-bottom:16px;font-size:14px;color:var(--gray)">Training Callbacks</p>
  <div class="feat-grid">
    <div class="feat-item">
      <div class="feat-dot teal"></div>
      <div><div class="feat-name">EarlyStopping</div><div class="feat-sub">Halts training when val_loss stops improving</div></div>
    </div>
    <div class="feat-item">
      <div class="feat-dot teal"></div>
      <div><div class="feat-name">ReduceLROnPlateau</div><div class="feat-sub">Lowers learning rate on stagnant epochs</div></div>
    </div>
    <div class="feat-item">
      <div class="feat-dot teal"></div>
      <div><div class="feat-name">ModelCheckpoint</div><div class="feat-sub">Saves the best model weights automatically</div></div>
    </div>
    <div class="feat-item">
      <div class="feat-dot teal"></div>
      <div><div class="feat-name">80 / 20 Split</div><div class="feat-sub">Stratified train/validation separation</div></div>
    </div>
  </div>
</section>

<hr class="divider">

<!-- ══════════ PROJECT 3 ══════════ -->
<section class="project-detail">
  <div class="detail-header">
    <div class="detail-icon icon-coral">🎗️</div>
    <div class="detail-meta">
      <h2>Breast Cancer Detection</h2>
      <p>Notebook: <code>Brest_cancer.ipynb</code> · Dataset: sklearn built-in (569 samples)</p>
    </div>
  </div>

  <div class="stat-row">
    <div class="stat-box"><div class="stat-label">Total Samples</div><div class="stat-val coral">569</div></div>
    <div class="stat-box"><div class="stat-label">Features</div><div class="stat-val coral">30</div></div>
    <div class="stat-box"><div class="stat-label">Best Accuracy</div><div class="stat-val coral">98.2%</div></div>
  </div>

  <p style="margin-bottom:16px;font-size:14px;color:var(--gray)">Model Benchmark — Test Accuracy</p>
  <div class="leaderboard">
    <div class="lb-row">
      <span class="lb-rank gold">🥇</span>
      <span class="lb-name">Support Vector Machine (SVM)</span>
      <div class="lb-bar-wrap"><div class="lb-bar coral" style="width:100%"></div></div>
      <span class="lb-acc">98.2%</span>
    </div>
    <div class="lb-row">
      <span class="lb-rank silver">🥈</span>
      <span class="lb-name">Logistic Regression</span>
      <div class="lb-bar-wrap"><div class="lb-bar coral" style="width:97%"></div></div>
      <span class="lb-acc">97.4%</span>
    </div>
    <div class="lb-row">
      <span class="lb-rank bronze">🥉</span>
      <span class="lb-name">Random Forest</span>
      <div class="lb-bar-wrap"><div class="lb-bar coral" style="width:94%"></div></div>
      <span class="lb-acc">96.5%</span>
    </div>
    <div class="lb-row">
      <span class="lb-rank" style="color:#94a3b8">4</span>
      <span class="lb-name">Naive Bayes</span>
      <div class="lb-bar-wrap"><div class="lb-bar coral" style="width:94%"></div></div>
      <span class="lb-acc">96.5%</span>
    </div>
    <div class="lb-row">
      <span class="lb-rank" style="color:#94a3b8">5</span>
      <span class="lb-name">Gradient Boosting</span>
      <div class="lb-bar-wrap"><div class="lb-bar coral" style="width:92%"></div></div>
      <span class="lb-acc">95.6%</span>
    </div>
    <div class="lb-row">
      <span class="lb-rank" style="color:#94a3b8">6</span>
      <span class="lb-name">K-Nearest Neighbors</span>
      <div class="lb-bar-wrap"><div class="lb-bar coral" style="width:88%"></div></div>
      <span class="lb-acc">94.7%</span>
    </div>
    <div class="lb-row">
      <span class="lb-rank" style="color:#94a3b8">7</span>
      <span class="lb-name">Decision Tree</span>
      <div class="lb-bar-wrap"><div class="lb-bar coral" style="width:88%"></div></div>
      <span class="lb-acc">94.7%</span>
    </div>
  </div>
</section>

<hr class="divider">

<!-- ══════════ PROJECT 4 ══════════ -->
<section class="project-detail">
  <div class="detail-header">
    <div class="detail-icon icon-blue">💳</div>
    <div class="detail-meta">
      <h2>Credit Score Classification</h2>
      <p>Notebook: <code>credit_score.ipynb</code> · Task: Good / Standard / Poor prediction</p>
    </div>
  </div>

  <div class="stat-row">
    <div class="stat-box"><div class="stat-label">Target Classes</div><div class="stat-val blue">3</div></div>
    <div class="stat-box"><div class="stat-label">New Features</div><div class="stat-val blue">5</div></div>
    <div class="stat-box"><div class="stat-label">Models Tested</div><div class="stat-val blue">6</div></div>
  </div>

  <p style="margin-bottom:16px;font-size:14px;color:var(--gray)">Engineered Features</p>
  <div class="feat-grid">
    <div class="feat-item">
      <div class="feat-dot blue"></div>
      <div><div class="feat-name">Debt_to_Income</div><div class="feat-sub">Outstanding Debt ÷ Annual Income</div></div>
    </div>
    <div class="feat-item">
      <div class="feat-dot blue"></div>
      <div><div class="feat-name">EMI_to_Salary</div><div class="feat-sub">Total EMI ÷ Monthly Salary</div></div>
    </div>
    <div class="feat-item">
      <div class="feat-dot blue"></div>
      <div><div class="feat-name">Savings_Ratio</div><div class="feat-sub">Amount Invested ÷ Monthly Salary</div></div>
    </div>
    <div class="feat-item">
      <div class="feat-dot blue"></div>
      <div><div class="feat-name">High_Utilization</div><div class="feat-sub">Credit Utilization &gt; 30% flag (0 / 1)</div></div>
    </div>
    <div class="feat-item">
      <div class="feat-dot blue"></div>
      <div><div class="feat-name">Has_Delayed</div><div class="feat-sub">Any delayed payments flag (0 / 1)</div></div>
    </div>
    <div class="feat-item">
      <div class="feat-dot blue"></div>
      <div><div class="feat-name">RobustScaler</div><div class="feat-sub">Outlier-resistant feature normalization</div></div>
    </div>
  </div>

  <p style="margin-bottom:16px;font-size:14px;color:var(--gray)">Models Benchmarked</p>
  <div class="leaderboard">
    <div class="lb-row"><span class="lb-rank gold">🥇</span><span class="lb-name">XGBoost Classifier</span><div class="lb-bar-wrap"><div class="lb-bar blue" style="width:100%"></div></div><span class="lb-acc">Best</span></div>
    <div class="lb-row"><span class="lb-rank silver">🥈</span><span class="lb-name">Random Forest (200 trees)</span><div class="lb-bar-wrap"><div class="lb-bar blue" style="width:95%"></div></div><span class="lb-acc">—</span></div>
    <div class="lb-row"><span class="lb-rank bronze">🥉</span><span class="lb-name">Extra Trees</span><div class="lb-bar-wrap"><div class="lb-bar blue" style="width:90%"></div></div><span class="lb-acc">—</span></div>
    <div class="lb-row"><span class="lb-rank" style="color:#94a3b8">4</span><span class="lb-name">Gradient Boosting</span><div class="lb-bar-wrap"><div class="lb-bar blue" style="width:85%"></div></div><span class="lb-acc">—</span></div>
    <div class="lb-row"><span class="lb-rank" style="color:#94a3b8">5</span><span class="lb-name">Decision Tree</span><div class="lb-bar-wrap"><div class="lb-bar blue" style="width:72%"></div></div><span class="lb-acc">—</span></div>
    <div class="lb-row"><span class="lb-rank" style="color:#94a3b8">6</span><span class="lb-name">Logistic Regression</span><div class="lb-bar-wrap"><div class="lb-bar blue" style="width:60%"></div></div><span class="lb-acc">—</span></div>
  </div>

  <div class="code-block">
<span class="cm"># Best model is auto-selected and predictions saved</span>
best_model_name = results_df.<span class="fn">iloc</span>[<span class="num">0</span>][<span class="str">'Model'</span>]
best_model      = models[best_model_name]
output = pd.<span class="fn">DataFrame</span>({
    <span class="str">'Credit_Score'</span>: le_target.<span class="fn">inverse_transform</span>(<span class="fn">test_pred</span>)
})
output.<span class="fn">to_csv</span>(<span class="str">'predictions.csv'</span>, index=<span class="kw">False</span>)
  </div>
</section>

<!-- ══════════ GETTING STARTED ══════════ -->
<section class="get-started">
  <div class="gs-inner">
    <p class="hero-eyebrow" style="color:#a78bfa"><span style="display:inline-block;width:28px;height:1px;background:#a78bfa"></span> Setup</p>
    <h2>Get Running in 3 Steps</h2>
    <p>Clone, install, and explore any notebook — zero configuration needed.</p>
    <div class="steps">
      <div class="step">
        <div class="step-num">STEP 01</div>
        <h3>Clone the Repo</h3>
        <p style="font-size:13px;color:#94a3b8;margin-bottom:0">Download all notebooks to your machine.</p>
        <div class="step-code">git clone https://github.com/your-username/ml-portfolio.git</div>
      </div>
      <div class="step">
        <div class="step-num">STEP 02</div>
        <h3>Install Dependencies</h3>
        <p style="font-size:13px;color:#94a3b8;margin-bottom:0">One command covers all four projects.</p>
        <div class="step-code">pip install tensorflow scikit-learn xgboost pandas numpy matplotlib seaborn</div>
      </div>
      <div class="step">
        <div class="step-num">STEP 03</div>
        <h3>Launch Jupyter</h3>
        <p style="font-size:13px;color:#94a3b8;margin-bottom:0">Open any notebook and run all cells.</p>
        <div class="step-code">jupyter notebook</div>
      </div>
    </div>
  </div>
</section>

<!-- ══════════ FOOTER ══════════ -->
<footer>
  <p>Built with Python 3.12 · TensorFlow · Scikit-Learn · XGBoost</p>
  <div class="footer-tags">
    <span class="tag tag-purple">Machine Learning</span>
    <span class="tag tag-teal">Deep Learning</span>
    <span class="tag tag-coral">Medical AI</span>
    <span class="tag tag-blue">FinTech</span>
  </div>
</footer>

</body>
</html>
