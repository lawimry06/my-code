<!DOCTYPE html>

<html lang="en">

<head>

  <meta charset="UTF-8" />

  <meta name="viewport" content="width=device-width, initial-scale=1.0" />



  <title>NovaFlow — Web3, Simplified</title>



  <meta

    name="description"

    content="NovaFlow is a modern Web3 platform for exploring, managing and interacting with digital assets."

  />



  <style>

    * {

      margin: 0;

      padding: 0;

      box-sizing: border-box;

    }



    :root {

      --bg: #05060a;

      --card: rgba(255, 255, 255, 0.055);

      --border: rgba(255, 255, 255, 0.1);

      --text: #ffffff;

      --muted: #9297a7;

      --accent: #8b5cf6;

      --accent2: #06b6d4;

      --green: #22c55e;

    }



    html {

      scroll-behavior: smooth;

    }



    body {

      font-family: Inter, Arial, sans-serif;

      background:

        radial-gradient(circle at 15% 10%, rgba(139, 92, 246, .18), transparent 30%),

        radial-gradient(circle at 85% 25%, rgba(6, 182, 212, .13), transparent 30%),

        var(--bg);

      color: var(--text);

      min-height: 100vh;

      overflow-x: hidden;

    }



    body::before {

      content: "";

      position: fixed;

      inset: 0;

      pointer-events: none;

      background-image:

        linear-gradient(rgba(255,255,255,.018) 1px, transparent 1px),

        linear-gradient(90deg, rgba(255,255,255,.018) 1px, transparent 1px);

      background-size: 50px 50px;

      mask-image: linear-gradient(to bottom, black, transparent);

      z-index: -2;

    }



    a {

      color: inherit;

      text-decoration: none;

    }



    button {

      font-family: inherit;

    }



    /* ---------------- NAVBAR ---------------- */



    nav {

      position: fixed;

      top: 18px;

      left: 50%;

      transform: translateX(-50%);

      width: min(1150px, calc(100% - 32px));

      padding: 13px 16px 13px 22px;

      border: 1px solid var(--border);

      border-radius: 20px;

      background: rgba(7, 8, 13, .72);

      backdrop-filter: blur(20px);

      display: flex;

      justify-content: space-between;

      align-items: center;

      z-index: 100;

    }



    .logo {

      display: flex;

      align-items: center;

      gap: 10px;

      font-size: 19px;

      font-weight: 800;

      letter-spacing: -.5px;

    }



    .logo-mark {

      width: 34px;

      height: 34px;

      border-radius: 11px;

      display: grid;

      place-items: center;

      background: linear-gradient(135deg, var(--accent), var(--accent2));

      box-shadow: 0 0 30px rgba(139,92,246,.35);

    }



    .logo-mark span {

      font-size: 18px;

      font-weight: 900;

    }



    .nav-links {

      display: flex;

      gap: 30px;

      color: #aaaebe;

      font-size: 14px;

    }



    .nav-links a {

      transition: .25s;

    }



    .nav-links a:hover {

      color: white;

    }



    .connect-btn {

      border: 0;

      cursor: pointer;

      padding: 11px 18px;

      border-radius: 12px;

      color: white;

      font-weight: 700;

      background: linear-gradient(135deg, #8b5cf6, #6366f1);

      box-shadow: 0 8px 25px rgba(99,102,241,.25);

      transition: .25s;

    }



    .connect-btn:hover {

      transform: translateY(-2px);

      box-shadow: 0 12px 35px rgba(99,102,241,.4);

    }



    /* ---------------- HERO ---------------- */



    .hero {

      width: min(1150px, calc(100% - 32px));

      min-height: 820px;

      margin: auto;

      padding-top: 180px;

      display: grid;

      grid-template-columns: 1.05fr .95fr;

      align-items: center;

      gap: 70px;

    }



    .badge {

      display: inline-flex;

      align-items: center;

      gap: 8px;

      padding: 8px 12px;

      border: 1px solid rgba(139,92,246,.25);

      border-radius: 100px;

      background: rgba(139,92,246,.07);

      color: #c4b5fd;

      font-size: 12px;

      margin-bottom: 24px;

    }



    .badge-dot {

      width: 7px;

      height: 7px;

      border-radius: 50%;

      background: #22c55e;

      box-shadow: 0 0 12px #22c55e;

    }



    .hero h1 {

      font-size: clamp(48px, 7vw, 88px);

      line-height: .98;

      letter-spacing: -5px;

      max-width: 720px;

    }



    .gradient-text {

      background: linear-gradient(

        90deg,

        #fff,

        #a78bfa,

        #67e8f9

      );

      -webkit-background-clip: text;

      background-clip: text;

      color: transparent;

    }



    .hero-description {

      margin-top: 28px;

      max-width: 570px;

      color: var(--muted);

      font-size: 17px;

      line-height: 1.8;

    }



    .hero-actions {

      margin-top: 35px;

      display: flex;

      gap: 13px;

      flex-wrap: wrap;

    }



    .primary-btn,

    .secondary-btn {

      padding: 15px 22px;

      border-radius: 13px;

      font-weight: 700;

      cursor: pointer;

      transition: .25s;

    }



    .primary-btn {

      border: 0;

      color: white;

      background: linear-gradient(135deg, #8b5cf6, #06b6d4);

      box-shadow: 0 15px 40px rgba(99,102,241,.25);

    }



    .secondary-btn {

      color: white;

      border: 1px solid var(--border);

      background: rgba(255,255,255,.045);

    }



    .primary-btn:hover,

    .secondary-btn:hover {

      transform: translateY(-3px);

    }



    /* ---------------- ORBIT ---------------- */



    .visual {

      height: 530px;

      position: relative;

      display: grid;

      place-items: center;

    }



    .orb {

      width: 290px;

      height: 290px;

      border-radius: 50%;

      background:

        radial-gradient(circle at 35% 30%, #c4b5fd, #8b5cf6 25%, #312e81 60%, #09090b 75%);

      box-shadow:

        0 0 70px rgba(139,92,246,.35),

        inset -30px -30px 70px rgba(0,0,0,.5);

      animation: float 5s ease-in-out infinite;

      position: relative;

      z-index: 2;

    }



    .orb::after {

      content: "";

      position: absolute;

      inset: -28px;

      border: 1px solid rgba(167,139,250,.18);

      border-radius: 50%;

      box-shadow: 0 0 50px rgba(139,92,246,.08);

    }



    .orbit {

      position: absolute;

      width: 450px;

      height: 450px;

      border: 1px solid rgba(255,255,255,.08);

      border-radius: 50%;

      transform: rotateX(65deg) rotateZ(-20deg);

      animation: spin 15s linear infinite;

    }



    .orbit.two {

      width: 370px;

      height: 370px;

      transform: rotateX(65deg) rotateZ(40deg);

      animation-duration: 11s;

      animation-direction: reverse;

    }



    .node {

      position: absolute;

      width: 18px;

      height: 18px;

      border-radius: 50%;

      background: #67e8f9;

      box-shadow: 0 0 25px #67e8f9;

    }



    .node.one {

      top: 5%;

      left: 28%;

    }



    .node.two {

      right: 2%;

      bottom: 25%;

      background: #a78bfa;

      box-shadow: 0 0 25px #a78bfa;

    }



    .floating-card {

      position: absolute;

      padding: 16px;

      border-radius: 16px;

      background: rgba(15,16,24,.75);

      border: 1px solid var(--border);

      backdrop-filter: blur(18px);

      z-index: 4;

      box-shadow: 0 20px 60px rgba(0,0,0,.3);

    }



    .floating-card.small {

      width: 170px;

      top: 55px;

      right: 5px;

    }



    .floating-card.bottom {

      width: 200px;

      bottom: 70px;

      left: 0;

    }



    .floating-label {

      color: #858a9b;

      font-size: 11px;

      margin-bottom: 7px;

    }



    .floating-value {

      font-size: 20px;

      font-weight: 800;

    }



    .positive {

      color: #4ade80;

      font-size: 12px;

      margin-top: 5px;

    }



    @keyframes float {

      0%,100% {

        transform: translateY(0);

      }



      50% {

        transform: translateY(-18px);

      }

    }



    @keyframes spin {

      from {

        transform: rotateX(65deg) rotateZ(0deg);

      }



      to {

        transform: rotateX(65deg) rotateZ(360deg);

      }

    }



    /* ---------------- STATS ---------------- */



    .stats {

      width: min(1150px, calc(100% - 32px));

      margin: -40px auto 120px;

      display: grid;

      grid-template-columns: repeat(4, 1fr);

      border: 1px solid var(--border);

      border-radius: 20px;

      overflow: hidden;

      background: rgba(255,255,255,.025);

    }



    .stat {

      padding: 28px;

      border-right: 1px solid var(--border);

    }



    .stat:last-child {

      border-right: 0;

    }



    .stat-number {

      font-size: 27px;

      font-weight: 800;

    }



    .stat-label {

      color: var(--muted);

      margin-top: 7px;

      font-size: 13px;

    }



    /* ---------------- SECTION ---------------- */



    section {

      width: min(1150px, calc(100% - 32px));

      margin: 0 auto 150px;

    }



    .section-header {

      max-width: 650px;

      margin-bottom: 45px;

    }



    .eyebrow {

      text-transform: uppercase;

      letter-spacing: 2px;

      font-size: 11px;

      color: #a78bfa;

      font-weight: 700;

      margin-bottom: 14px;

    }



    .section-header h2 {

      font-size: clamp(34px, 5vw, 54px);

      letter-spacing: -2px;

      line-height: 1.05;

    }



    .section-header p {

      color: var(--muted);

      margin-top: 16px;

      line-height: 1.7;

    }



    /* ---------------- FEATURE CARDS ---------------- */



    .features {

      display: grid;

      grid-template-columns: repeat(3, 1fr);

      gap: 16px;

    }



    .feature {

      min-height: 270px;

      padding: 27px;

      border: 1px solid var(--border);

      border-radius: 20px;

      background: linear-gradient(

        145deg,

        rgba(255,255,255,.06),

        rgba(255,255,255,.02)

      );

      transition: .3s;

      position: relative;

      overflow: hidden;

    }



    .feature::before {

      content: "";

      position: absolute;

      width: 130px;

      height: 130px;

      border-radius: 50%;

      background: rgba(139,92,246,.12);

      filter: blur(30px);

      top: -50px;

      right: -50px;

    }



    .feature:hover {

      transform: translateY(-7px);

      border-color: rgba(167,139,250,.35);

    }



    .feature-icon {

      width: 48px;

      height: 48px;

      border-radius: 14px;

      display: grid;

      place-items: center;

      font-size: 21px;

      background: rgba(139,92,246,.12);

      border: 1px solid rgba(139,92,246,.15);

      margin-bottom: 30px;

    }



    .feature h3 {

      font-size: 19px;

      margin-bottom: 11px;

    }



    .feature p {

      color: var(--muted);

      line-height: 1.65;

      font-size: 14px;

    }



    /* ---------------- DASHBOARD ---------------- */



    .dashboard {

      border: 1px solid var(--border);

      border-radius: 24px;

      padding: 20px;

      background: rgba(255,255,255,.035);

      box-shadow: 0 30px 100px rgba(0,0,0,.25);

    }



    .dashboard-top {

      display: flex;

      justify-content: space-between;

      align-items: center;

      margin-bottom: 18px;

    }



    .dashboard-title {

      font-size: 18px;

      font-weight: 700;

    }



    .live {

      display: flex;

      align-items: center;

      gap: 7px;

      color: #4ade80;

      font-size: 12px;

    }



    .live span {

      width: 7px;

      height: 7px;

      background: #22c55e;

      border-radius: 50%;

      box-shadow: 0 0 12px #22c55e;

    }



    .dashboard-grid {

      display: grid;

      grid-template-columns: 1.5fr .8fr;

      gap: 16px;

    }



    .chart-box,

    .portfolio {

      border: 1px solid var(--border);

      background: rgba(0,0,0,.18);

      border-radius: 17px;

      padding: 22px;

    }



    .balance {

      color: var(--muted);

      font-size: 12px;

    }



    .balance-value {

      font-size: 32px;

      font-weight: 800;

      margin-top: 8px;

    }



    .chart {

      height: 180px;

      margin-top: 25px;

      position: relative;

      overflow: hidden;

    }



    .chart svg {

      width: 100%;

      height: 100%;

    }



    .portfolio-item {

      display: flex;

      justify-content: space-between;

      padding: 15px 0;

      border-bottom: 1px solid rgba(255,255,255,.06);

    }



    .portfolio-item:last-child {

      border-bottom: 0;

    }



    .coin {

      display: flex;

      gap: 10px;

      align-items: center;

    }



    .coin-icon {

      width: 32px;

      height: 32px;

      border-radius: 50%;

      display: grid;

      place-items: center;

      background: rgba(255,255,255,.08);

    }



    .coin-name {

      font-size: 13px;

      font-weight: 700;

    }



    .coin-symbol {

      font-size: 10px;

      color: var(--muted);

      margin-top: 2px;

    }



    .coin-price {

      text-align: right;

      font-size: 13px;

    }



    /* ---------------- STEPS ---------------- */



    .steps {

      display: grid;

      grid-template-columns: repeat(3, 1fr);

      gap: 18px;

    }



    .step {

      padding: 30px;

      border-radius: 20px;

      border: 1px solid var(--border);

      background: rgba(255,255,255,.03);

    }



    .step-number {

      font-size: 13px;

      color: #a78bfa;

      margin-bottom: 30px;

    }



    .step h3 {

      font-size: 20px;

      margin-bottom: 12px;

    }



    .step p {

      color: var(--muted);

      line-height: 1.7;

      font-size: 14px;

    }



    /* ---------------- CTA ---------------- */



    .cta {

      position: relative;

      overflow: hidden;

      padding: 80px 40px;

      text-align: center;

      border-radius: 28px;

      border: 1px solid var(--border);

      background:

        radial-gradient(circle at 50% 120%, rgba(139,92,246,.3), transparent 50%),

        rgba(255,255,255,.035);

    }



    .cta h2 {

      font-size: clamp(35px, 5vw, 60px);

      letter-spacing: -2px;

    }



    .cta p {

      max-width: 570px;

      margin: 18px auto 30px;

      color: var(--muted);

      line-height: 1.7;

    }



    /* ---------------- FAQ ---------------- */



    .faq {

      max-width: 800px;

      margin: auto;

    }



    .faq-item {

      border-bottom: 1px solid var(--border);

    }



    .faq-question {

      width: 100%;

      border: 0;

      background: none;

      color: white;

      text-align: left;

      padding: 23px 5px;

      cursor: pointer;

      font-size: 16px;

      display: flex;

      justify-content: space-between;

      align-items: center;

    }



    .faq-answer {

      max-height: 0;

      overflow: hidden;

      transition: .3s;

      color: var(--muted);

      line-height: 1.7;

      font-size: 14px;

    }



    .faq-item.active .faq-answer {

      max-height: 200px;

      padding-bottom: 20px;

    }



    .faq-icon {

      font-size: 20px;

      transition: .3s;

    }



    .faq-item.active .faq-icon {

      transform: rotate(45deg);

    }



    /* ---------------- FOOTER ---------------- */



    footer {

      width: min(1150px, calc(100% - 32px));

      margin: auto;

      padding: 35px 0 50px;

      border-top: 1px solid var(--border);

      display: flex;

      justify-content: space-between;

      color: var(--muted);

      font-size: 12px;

    }



    .footer-links {

      display: flex;

      gap: 22px;

    }



    /* ---------------- MODAL ---------------- */



    .modal {

      position: fixed;

      inset: 0;

      background: rgba(0,0,0,.72);

      backdrop-filter: blur(10px);

      display: none;

      place-items: center;

      z-index: 500;

      padding: 20px;

    }



    .modal.show {

      display: grid;

    }



    .wallet-modal {

      width: min(430px, 100%);

      padding: 27px;

      border-radius: 24px;

      border: 1px solid var(--border);

      background: #0b0c12;

      box-shadow: 0 40px 120px rgba(0,0,0,.6);

      animation: modalIn .25s ease;

    }



    @keyframes modalIn {

      from {

        opacity: 0;

        transform: translateY(15px) scale(.97);

      }

      to {

        opacity: 1;

        transform: translateY(0) scale(1);

      }

    }



    .modal-header {

      display: flex;

      justify-content: space-between;

      align-items: center;

      margin-bottom: 22px;

    }



    .modal-header h3 {

      font-size: 20px;

    }



    .close {

      width: 32px;

      height: 32px;

      border-radius: 10px;

      border: 1px solid var(--border);

      background: rgba(255,255,255,.05);

      color: white;

      cursor: pointer;

    }



    .wallet-option {

      width: 100%;

      padding: 15px;

      margin-bottom: 10px;

      border-radius: 14px;

      border: 1px solid var(--border);

      background: rgba(255,255,255,.035);

      color: white;

      cursor: pointer;

      display: flex;

      align-items: center;

      gap: 13px;

      transition: .2s;

    }



    .wallet-option:hover {

      background: rgba(139,92,246,.1);

      border-color: rgba(139,92,246,.3);

    }



    .wallet-logo {

      width: 37px;

      height: 37px;

      display: grid;

      place-items: center;

      border-radius: 11px;

      background: rgba(255,255,255,.08);

      font-size: 18px;

    }



    .wallet-modal {
      max-height: min(760px, calc(100vh - 40px));
      overflow: hidden;
    }

    .wallet-search-wrap {
      position: relative;
      display: flex;
      align-items: center;
      gap: 8px;
      margin-bottom: 13px;
    }

    .wallet-search-icon {
      position: absolute;
      left: 13px;
      color: #8f94a5;
      font-size: 18px;
      pointer-events: none;
    }

    .wallet-search {
      width: 100%;
      min-width: 0;
      padding: 12px 86px 12px 38px;
      border: 1px solid var(--border);
      border-radius: 12px;
      background: rgba(255,255,255,.045);
      color: white;
      outline: none;
    }

    .wallet-search:focus {
      border-color: rgba(139,92,246,.5);
      box-shadow: 0 0 0 3px rgba(139,92,246,.08);
    }

    .wallet-search::placeholder {
      color: #777d8d;
    }

    .wallet-count {
      position: absolute;
      right: 11px;
      color: #777d8d;
      font-size: 10px;
      pointer-events: none;
    }

    .wallet-list {
      max-height: 500px;
      overflow-y: auto;
      padding-right: 4px;
    }

    .wallet-list::-webkit-scrollbar {
      width: 6px;
    }

    .wallet-list::-webkit-scrollbar-thumb {
      background: rgba(255,255,255,.12);
      border-radius: 99px;
    }

    .wallet-name-wrap {
      text-align: left;
      min-width: 0;
    }

    .wallet-network {
      font-size: 11px;
      color: #777d8d;
      margin-top: 3px;
    }

    .wallet-fallback {
      display: none;
      width: 100%;
      height: 100%;
      place-items: center;
      font-size: 11px;
      font-weight: 800;
    }

    .wallet-logo img {
      width: 24px;
      height: 24px;
      object-fit: contain;
    }

    .wallet-empty {
      display: none;
      padding: 20px;
      text-align: center;
      color: #8f94a5;
      font-size: 13px;
    }

    .security-note {

      margin-top: 18px;

      padding: 13px;

      border-radius: 12px;

      background: rgba(34,197,94,.06);

      border: 1px solid rgba(34,197,94,.12);

      color: #86efac;

      font-size: 11px;

      line-height: 1.5;

    }



    /* ---------------- RESPONSIVE ---------------- */



    @media (max-width: 850px) {



      .nav-links {

        display: none;

      }



      .hero {

        grid-template-columns: 1fr;

        padding-top: 140px;

        min-height: auto;

        gap: 50px;

      }



      .hero h1 {

        letter-spacing: -3px;

      }



      .visual {

        height: 470px;

      }



      .stats {

        grid-template-columns: repeat(2, 1fr);

        margin-top: 70px;

      }



      .stat:nth-child(2) {

        border-right: 0;

      }



      .stat:nth-child(-n+2) {

        border-bottom: 1px solid var(--border);

      }



      .features,

      .steps {

        grid-template-columns: 1fr;

      }



      .dashboard-grid {

        grid-template-columns: 1fr;

      }



      footer {

        flex-direction: column;

        gap: 20px;

      }

    }



    @media (max-width: 520px) {



      nav {

        width: calc(100% - 20px);

        top: 10px;

      }



      .hero {

        width: calc(100% - 24px);

      }



      section,

      .stats {

        width: calc(100% - 24px);

      }



      .hero h1 {

        font-size: 48px;

      }



      .orb {

        width: 220px;

        height: 220px;

      }



      .orbit {

        width: 330px;

        height: 330px;

      }



      .orbit.two {

        width: 280px;

        height: 280px;

      }



      .floating-card.small {

        right: -5px;

      }



      .floating-card.bottom {

        left: -5px;

      }



      .stats {

        grid-template-columns: 1fr 1fr;

      }



      .stat {

        padding: 20px 15px;

      }



      .stat-number {

        font-size: 21px;

      }



      .cta {

        padding: 55px 20px;

      }

    }

  </style>

</head>



<body>



  <!-- NAVIGATION -->



  <nav>



    <a href="#" class="logo">

      <div class="logo-mark">

        <span>N</span>

      </div>



      NovaFlow

    </a>



    <div class="nav-links">

      <a href="#features">Features</a>

      <a href="#dashboard">Dashboard</a>

      <a href="#how">How it works</a>

      <a href="#faq">FAQ</a>

    </div>



    <button class="connect-btn" onclick="openWallet()">

      Connect

    </button>



  </nav>





  <!-- HERO -->



  <main>



    <div class="hero">



      <div>



        <div class="badge">

          <span class="badge-dot"></span>

          The next generation of Web3

        </div>



        <h1>

          Your gateway to the

          <span class="gradient-text">

            on-chain world.

          </span>

        </h1>



        <p class="hero-description">

          Explore digital assets, monitor your portfolio and

          interact with decentralized applications through one

          beautifully designed Web3 experience.

        </p>



        <div class="hero-actions">



          <button

            class="primary-btn"

            onclick="openWallet()"

          >

            Connect Wallet →

          </button>



          <a href="#features" class="secondary-btn">

            Explore platform

          </a>



        </div>



      </div>





      <!-- 3D VISUAL -->



      <div class="visual">



        <div class="orbit">

          <div class="node one"></div>

        </div>



        <div class="orbit two">

          <div class="node two"></div>

        </div>



        <div class="orb"></div>





        <div class="floating-card small">



          <div class="floating-label">

            Network activity

          </div>



          <div class="floating-value">

            24.8K

          </div>



          <div class="positive">

            +18.4% today

          </div>



        </div>





        <div class="floating-card bottom">



          <div class="floating-label">

            Portfolio value

          </div>



          <div class="floating-value">

            $48,291.64

          </div>



          <div class="positive">

            +6.82%

          </div>



        </div>



      </div>



    </div>





    <!-- STATS -->



    <div class="stats">



      <div class="stat">

        <div class="stat-number">128K+</div>

        <div class="stat-label">Active users</div>

      </div>



      <div class="stat">

        <div class="stat-number">$2.8B</div>

        <div class="stat-label">Assets tracked</div>

      </div>



      <div class="stat">

        <div class="stat-number">42+</div>

        <div class="stat-label">Networks</div>

      </div>



      <div class="stat">

        <div class="stat-number">99.99%</div>

        <div class="stat-label">Platform uptime</div>

      </div>



    </div>





    <!-- FEATURES -->



    <section id="features">



      <div class="section-header">



        <div class="eyebrow">

          Everything in one place

        </div>



        <h2>

          Built for the way

          Web3 should feel.

        </h2>



        <p>

          A cleaner interface for navigating decentralized

          applications and managing your on-chain activity.

        </p>



      </div>





      <div class="features">



        <div class="feature">



          <div class="feature-icon">

            ◈

          </div>



          <h3>

            Portfolio

          </h3>



          <p>

            See your digital assets across supported networks

            from a single, easy-to-understand dashboard.

          </p>



        </div>





        <div class="feature">



          <div class="feature-icon">

            ⇄

          </div>



          <h3>

            Swap

          </h3>



          <p>

            Discover token exchange opportunities through a

            streamlined decentralized trading interface.

          </p>



        </div>





        <div class="feature">



          <div class="feature-icon">

            ◎

          </div>



          <h3>

            Explore

          </h3>



          <p>

            Discover decentralized applications and blockchain

            ecosystems without jumping between multiple tools.

          </p>



        </div>





        <div class="feature">



          <div class="feature-icon">

            ◉

          </div>



          <h3>

            Analytics

          </h3>



          <p>

            Understand wallet activity, balances and network

            movements with clear visual insights.

          </p>



        </div>





        <div class="feature">



          <div class="feature-icon">

            ⚡

          </div>



          <h3>

            Fast

          </h3>



          <p>

            A lightweight interface designed for quick access

            and smooth navigation across devices.

          </p>



        </div>





        <div class="feature">



          <div class="feature-icon">

            ♢

          </div>



          <h3>

            Secure by design

          </h3>



          <p>

            Your sensitive wallet credentials remain with your

            wallet provider.

          </p>



        </div>



      </div>



    </section>





    <!-- DASHBOARD -->



    <section id="dashboard">



      <div class="section-header">



        <div class="eyebrow">

          Your command center

        </div>



        <h2>

          See everything.

          Miss nothing.

        </h2>



      </div>





      <div class="dashboard">



        <div class="dashboard-top">



          <div class="dashboard-title">

            Portfolio overview

          </div>



          <div class="live">

            <span></span>

            Live data

          </div>



        </div>





        <div class="dashboard-grid">



          <div class="chart-box">



            <div class="balance">

              Total balance

            </div>



            <div class="balance-value">

              $48,291.64

            </div>



            <div class="positive">

              +$2,481.29 today

            </div>





            <div class="chart">



              <svg

                viewBox="0 0 700 180"

                preserveAspectRatio="none"

              >



                <defs>



                  <linearGradient

                    id="chartGradient"

                    x1="0"

                    x2="0"

                    y1="0"

                    y2="1"

                  >



                    <stop

                      offset="0%"

                      stop-color="#8b5cf6"

                      stop-opacity=".35"

                    />



                    <stop

                      offset="100%"

                      stop-color="#8b5cf6"

                      stop-opacity="0"

                    />



                  </linearGradient>



                </defs>



                <path

                  d="M0 145

                  C40 135 50 150 85 128

                  S130 110 165 123

                  S215 95 250 105

                  S290 80 330 92

                  S380 60 415 76

                  S460 65 490 72

                  S530 30 560 49

                  S610 35 640 42

                  S680 15 700 22

                  L700 180

                  L0 180 Z"

                  fill="url(#chartGradient)"

                />



                <path

                  d="M0 145

                  C40 135 50 150 85 128

                  S130 110 165 123

                  S215 95 250 105

                  S290 80 330 92

                  S380 60 415 76

                  S460 65 490 72

                  S530 30 560 49

                  S610 35 640 42

                  S680 15 700 22"

                  fill="none"

                  stroke="#a78bfa"

                  stroke-width="3"

                />



              </svg>



            </div>



          </div>





          <div class="portfolio">



            <div class="balance">

              Assets

            </div>





            <div class="portfolio-item">



              <div class="coin">



                <div class="coin-icon">

                  Ξ

                </div>



                <div>

                  <div class="coin-name">

                    Ethereum

                  </div>



                  <div class="coin-symbol">

                    ETH

                  </div>

                </div>



              </div>



              <div class="coin-price">

                $3,842

              </div>



            </div>





            <div class="portfolio-item">



              <div class="coin">



                <div class="coin-icon">

                  ₿

                </div>



                <div>

                  <div class="coin-name">

                    Bitcoin

                  </div>



                  <div class="coin-symbol">

                    BTC

                  </div>

                </div>



              </div>



              <div class="coin-price">

                $104K

              </div>



            </div>





            <div class="portfolio-item">



              <div class="coin">



                <div class="coin-icon">

                  ◎

                </div>



                <div>

                  <div class="coin-name">

                    Solana

                  </div>



                  <div class="coin-symbol">

                    SOL

                  </div>

                </div>



              </div>



              <div class="coin-price">

                $221

              </div>



            </div>





            <div class="portfolio-item">



              <div class="coin">



                <div class="coin-icon">

                  ◆

                </div>



                <div>

                  <div class="coin-name">

                    Polygon

                  </div>



                  <div class="coin-symbol">

                    POL

                  </div>



                </div>



              </div>



              <div class="coin-price">

                $0.41

              </div>



            </div>



          </div>



        </div>



      </div>



    </section>





    <!-- HOW IT WORKS -->



    <section id="how">



      <div class="section-header">



        <div class="eyebrow">

          Simple by design

        </div>



        <h2>

          Get started in minutes.

        </h2>



      </div>





      <div class="steps">



        <div class="step">



          <div class="step-number">

            01 / CONNECT

          </div>



          <h3>

            Connect your wallet

          </h3>



          <p>

            Choose a supported wallet provider and securely

            connect it to the application.

          </p>



        </div>





        <div class="step">



          <div class="step-number">

            02 / EXPLORE

          </div>



          <h3>

            Explore your assets

          </h3>



          <p>

            View balances, networks and on-chain activity

            through your personalized dashboard.

          </p>



        </div>





        <div class="step">



          <div class="step-number">

            03 / ACT

          </div>



          <h3>

            Take action

          </h3>



          <p>

            Explore supported Web3 applications and interact

            with decentralized services through your wallet.

          </p>



        </div>



      </div>



    </section>





    <!-- CTA -->



    <section>



      <div class="cta">



        <div class="eyebrow">

          Enter the next layer

        </div>



        <h2>

          Your wallet.

          Your world.

        </h2>



        <p>

          Start exploring the decentralized web through a

          simpler, faster and more beautiful interface.

        </p>



        <button

          class="primary-btn"

          onclick="openWallet()"

        >

          Connect Wallet →

        </button>



      </div>



    </section>





    <!-- FAQ -->



    <section id="faq">



      <div class="section-header">



        <div class="eyebrow">

          Questions

        </div>



        <h2>

          Frequently asked.

        </h2>



      </div>





      <div class="faq">



        <div class="faq-item">



          <button class="faq-question">

            What is NovaFlow?

            <span class="faq-icon">+</span>

          </button>



          <div class="faq-answer">

            NovaFlow is a Web3 interface concept designed to

            help users view assets and interact with decentralized

            applications from one place.

          </div>



        </div>





        <div class="faq-item">



          <button class="faq-question">

            Do you store my private keys?

            <span class="faq-icon">+</span>

          </button>



          <div class="faq-answer">

            No. A legitimate Web3 application should never ask

            you to submit your seed phrase or private key.

            Wallet authentication should be handled by your

            wallet provider.

          </div>



        </div>





        <div class="faq-item">



          <button class="faq-question">

            Can I use this on mobile?

            <span class="faq-icon">+</span>

          </button>



          <div class="faq-answer">

            Yes. The interface is responsive and adapts to

            desktop, tablet and mobile screen sizes.

          </div>



        </div>





        <div class="faq-item">



          <button class="faq-question">

            Can this connect to real wallets?

            <span class="faq-icon">+</span>

          </button>



          <div class="faq-answer">

            Yes. The current wallet selector is a front-end demo.

            You can later integrate a reputable wallet connection

            library and configure the supported networks.

          </div>



        </div>



      </div>



    </section>



  </main>





  <!-- FOOTER -->



  <footer>



    <div>

      © 2026 NovaFlow. Built for the decentralized web.

    </div>



    <div class="footer-links">

      <a href="#">Privacy</a>

      <a href="#">Terms</a>

      <a href="#">Docs</a>

    </div>



  </footer>





  <!-- WALLET MODAL -->



  <div class="modal" id="walletModal">



    <div class="wallet-modal">



      <div class="modal-header">



        <h3>

          Connect wallet

        </h3>



        <button

          class="close"

          onclick="closeWallet()"

        >

          ×

        </button>



      </div>





      <div class="wallet-search-wrap">

        <span class="wallet-search-icon">⌕</span>

        <input id="walletSearch" class="wallet-search" type="search" placeholder="Search wallets..." autocomplete="off" aria-label="Search wallets" />

        <span class="wallet-count">81 wallets</span>

      </div>

      <div id="walletList" class="wallet-list" aria-label="Supported wallets"></div>

      <div id="walletEmpty" class="wallet-empty"></div>


      <div class="security-note">

      </div>



    </div>



  </div>





  <script>



    /* ---------------- WALLET MODAL ---------------- */



    const modal = document.getElementById("walletModal");

    function openWallet() {
      renderWallets("");
      modal.classList.add("show");
      document.body.style.overflow = "hidden";
      setTimeout(() => document.getElementById("walletSearch")?.focus(), 50);
    }

    function closeWallet() {
      modal.classList.remove("show");
      document.body.style.overflow = "";
    }

    const walletCatalog = [
      { name: 'Phantom', slug: 'phantom', initials: 'PH' },
      { name: 'MetaMask', slug: 'metamask', initials: 'ME' },
      { name: 'Coinbase Wallet', slug: 'coinbase', initials: 'CW' },
      { name: 'WalletConnect', slug: 'walletconnect', initials: 'WA' },
      { name: 'Trust Wallet', slug: 'trustwallet', initials: 'TW' },
      { name: 'Chainge Wallet', slug: 'chainge', initials: 'CW' },
      { name: 'Moonshot Wallet', slug: 'moonshot', initials: 'MW' },
      { name: 'Sub Wallet', slug: 'subwallet', initials: 'SW' },
      { name: 'Best Wallet', slug: 'bestwallet', initials: 'BW' },
      { name: 'Hashpack', slug: 'hashpack', initials: 'HA' },
      { name: 'Keplr', slug: 'keplr', initials: 'KE' },
      { name: 'OKX Wallet', slug: 'okx', initials: 'OK' },
      { name: 'Klever', slug: 'klever', initials: 'KL' },
      { name: 'Solo Dex Wallet', slug: 'solodex', initials: 'SD' },
      { name: 'Fantom', slug: 'fantom', initials: 'FA' },
      { name: 'Blade', slug: 'blade', initials: 'BL' },
      { name: 'Rabby Wallet', slug: 'rabby', initials: 'RW' },
      { name: 'Torus Wallet', slug: 'torus', initials: 'TW' },
      { name: 'Cosmos', slug: 'cosmos', initials: 'CO' },
      { name: 'Slope Wallet', slug: 'slope', initials: 'SW' },
      { name: 'Flint Wallet', slug: 'flint', initials: 'FW' },
      { name: 'Binance Chain Wallet', slug: 'binance', initials: 'BC' },
      { name: 'Terra station', slug: 'terra', initials: 'TS' },
      { name: 'Polygon Wallet', slug: 'polygon', initials: 'PW' },
      { name: 'Rainbow', slug: 'rainbow', initials: 'RA' },
      { name: 'Bitpay', slug: 'bitpay', initials: 'BI' },
      { name: 'Walleth', slug: 'walleth', initials: 'WA' },
      { name: 'Argent', slug: 'argent', initials: 'AR' },
      { name: 'Huobi Wallet', slug: 'huobi', initials: 'HW' },
      { name: 'Encrypted Ink', slug: 'encryptedink', initials: 'EI' },
      { name: 'Compound', slug: 'compound', initials: 'CO' },
      { name: 'Polkadot', slug: 'polkadot', initials: 'PO' },
      { name: 'Iotex', slug: 'iotex', initials: 'IO' },
      { name: 'Coin98', slug: 'coin98', initials: 'CO' },
      { name: 'Coinbase', slug: 'coinbase', initials: 'CO' },
      { name: 'Crypto.com | Defi Wallet', slug: 'crypto', initials: 'CD' },
      { name: 'Token Pocket', slug: 'tokenpocket', initials: 'TP' },
      { name: 'Math Wallet', slug: 'mathwallet', initials: 'MW' },
      { name: 'Ledger Live', slug: 'ledger', initials: 'LL' },
      { name: '1Inch', slug: '1inch', initials: '1' },
      { name: 'Dharma', slug: 'dharma', initials: 'DH' },
      { name: 'Trust Vault', slug: 'trustwallet', initials: 'TV' },
      { name: 'MYKEY', slug: 'mykey', initials: 'MY' },
      { name: 'Atomic', slug: 'atomicwallet', initials: 'AT' },
      { name: 'CoolWallet S', slug: 'coolwallet', initials: 'CS' },
      { name: 'Nash', slug: 'nash', initials: 'NA' },
      { name: 'Coinomi', slug: 'coinomi', initials: 'CO' },
      { name: 'GridPlus', slug: 'gridplus', initials: 'GR' },
      { name: 'Tokenary', slug: 'tokenary', initials: 'TO' },
      { name: 'SafePal', slug: 'safepal', initials: 'SA' },
      { name: 'Infinito', slug: 'infinito', initials: 'IN' },
      { name: 'Wallet.io', slug: 'walletio', initials: 'WA' },
      { name: 'Ownbit', slug: 'ownbit', initials: 'OW' },
      { name: 'EasyPocket', slug: 'easypocket', initials: 'EA' },
      { name: 'Bridge Wallet', slug: 'bridgewallet', initials: 'BW' },
      { name: 'ViaWallet', slug: 'viawallet', initials: 'VI' },
      { name: 'BitKeep', slug: 'bitkeep', initials: 'BI' },
      { name: 'Unstoppable Wallet', slug: 'unstoppable', initials: 'UW' },
      { name: 'HaloDefi Wallet', slug: 'halodefi', initials: 'HW' },
      { name: 'Dok Wallet', slug: 'dokwallet', initials: 'DW' },
      { name: 'Cello Wallet', slug: 'celo', initials: 'CW' },
      { name: 'CoinUs', slug: 'coinus', initials: 'CO' },
      { name: 'Valora', slug: 'valora', initials: 'VA' },
      { name: 'Trustee Wallet', slug: 'trustee', initials: 'TW' },
      { name: 'Gaurda Wallet', slug: 'guarda', initials: 'GW' },
      { name: 'Maiar Wallet', slug: 'multiversx', initials: 'MW' },
      { name: 'Jade Wallet', slug: 'jade', initials: 'JW' },
      { name: 'PlasmaPay', slug: 'plasmapay', initials: 'PL' },
      { name: 'O3Wallet', slug: 'o3swap', initials: 'O3' },
      { name: 'HashKey Me', slug: 'hashkey', initials: 'HM' },
      { name: 'RWallet', slug: 'rwallet', initials: 'RW' },
      { name: 'Flare Wallet', slug: 'flare', initials: 'FW' },
      { name: 'KyberSwap', slug: 'kyberswap', initials: 'KY' },
      { name: 'AToken Wallet', slug: 'atoken', initials: 'AW' },
      { name: 'Tongue Wallet', slug: 'tongue', initials: 'TW' },
      { name: 'XinFin XDC Network', slug: 'xdc', initials: 'XX' },
      { name: 'Talken Wallet', slug: 'talken', initials: 'TW' },
      { name: 'KEYRING PRO', slug: 'keyring', initials: 'KP' },
      { name: 'Midas Wallet', slug: 'midas', initials: 'MW' },
      { name: 'AT.Wallet', slug: 'atwallet', initials: 'AT' },
      { name: 'imToken', slug: 'imtoken', initials: 'IM' }
    ];

    function renderWallets(filter = '') {
      const walletModal = document.querySelector('.wallet-modal');
      const securityNote = walletModal.querySelector('.security-note');
      const search = walletModal.querySelector('#walletSearch');
      const list = walletModal.querySelector('#walletList');
      const empty = walletModal.querySelector('#walletEmpty');
      if (!search || !list || !empty) return;

      if (!search.dataset.bound) {
        search.addEventListener('input', () => renderWallets(search.value));
        search.dataset.bound = 'true';
      }

      list.innerHTML = '';
      const query = filter.trim().toLowerCase();
      const visibleWallets = walletCatalog.filter(wallet => wallet.name.toLowerCase().includes(query));

      visibleWallets.forEach(wallet => {
        const button = document.createElement('button');
        button.className = 'wallet-option';
        button.type = 'button';
        button.setAttribute('data-wallet', wallet.name);
        button.onclick = () => selectWallet(wallet.name);
        button.innerHTML = `
          <div class="wallet-logo">
            <img src="https://cdn.simpleicons.org/${wallet.slug}" alt="" loading="lazy">
            <span class="wallet-fallback">${wallet.initials}</span>
          </div>
          <div class="wallet-name-wrap">
            <strong>${wallet.name}</strong>
            <div class="wallet-network">Wallet</div>
          </div>
        `;
        const icon = button.querySelector('img');
        icon.addEventListener('error', () => {
          icon.style.display = 'none';
          button.querySelector('.wallet-fallback').style.display = 'grid';
        });
        list.appendChild(button);
      });

      empty.textContent = query && visibleWallets.length === 0 ? 'No wallet found. Try another name.' : '';
      empty.style.display = query && visibleWallets.length === 0 ? 'block' : 'none';
      if (securityNote) {
        securityNote.textContent = ' ';
      }
    }

    function selectWallet(wallet) {
      alert(wallet + " selected.\n\n" + "This demo does not connect to a real wallet yet.");
    }

    modal.addEventListener("click", function(e) {



      if (e.target === modal) {

        closeWallet();

      }



    });





    /* ---------------- FAQ ---------------- */



    const faqQuestions =

      document.querySelectorAll(".faq-question");



    faqQuestions.forEach(question => {



      question.addEventListener("click", () => {



        const item =

          question.parentElement;



        const isActive =

          item.classList.contains("active");



        document

          .querySelectorAll(".faq-item")

          .forEach(other => {

            other.classList.remove("active");

          });



        if (!isActive) {

          item.classList.add("active");

        }



      });



    });





    /* ---------------- ESCAPE KEY ---------------- */



    document.addEventListener("keydown", e => {



      if (e.key === "Escape") {

        closeWallet();

      }



    });





    /* ---------------- SCROLL REVEAL ---------------- */



    const revealElements =

      document.querySelectorAll(

        ".feature, .step, .dashboard, .cta"

      );



    const observer =

      new IntersectionObserver(

        entries => {



          entries.forEach(entry => {



            if (entry.isIntersecting) {



              entry.target.style.opacity = "1";

              entry.target.style.transform =

                "translateY(0)";



            }



          });



        },

        {

          threshold: .12

        }

      );





    revealElements.forEach(el => {



      el.style.opacity = "0";

      el.style.transform = "translateY(25px)";

      el.style.transition =

        "opacity .7s ease, transform .7s ease";



      observer.observe(el);



    });



  </script>



</body>

</html>
