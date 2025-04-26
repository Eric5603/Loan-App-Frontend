<style>
    @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap');
  
    :root {
      /* Enhanced color palette */
      --primary: #3758F9;
      --primary-hover: #2648e6;
      --primary-dark: #1d3ec5;
      --primary-light: rgba(55, 88, 249, 0.1);
      --primary-bg: rgba(55, 88, 249, 0.03);
      --text: #1f2937;
      --text-light: #4b5563;
      --text-lighter: #9ca3af;
      --bg: #ffffff;
      --bg-alt: #f9fafb;
      --bg-dark: #0f172a;
      --border: #e5e7eb;
      --shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.05);
      --shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -2px rgba(0, 0, 0, 0.1);
      --shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -4px rgba(0, 0, 0, 0.1);
      --transition: 0.25s ease;
    }
  
    :global(body) {
      margin: 0;
      font-family: 'Inter', sans-serif;
      background: var(--bg);
      color: var(--text);
      line-height: 1.5;
      -webkit-font-smoothing: antialiased;
    }
  
    .hero {
      position: relative;
      padding: 7rem 1.5rem 6rem;
      background-color: var(--bg);
      color: var(--text);
      overflow: hidden;
    }
  
    /* Improved gradient background */
    .hero::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: 
        radial-gradient(circle at 5% 10%, var(--primary-light), transparent 50%),
        radial-gradient(circle at 95% 85%, rgba(241, 245, 249, 0.8), transparent 50%),
        radial-gradient(circle at 50% 50%, var(--primary-bg), transparent 70%);
      z-index: 0;
    }
  
    /* Added animated shapes for visual interest */
    .hero::after {
      content: '';
      position: absolute;
      width: 200px;
      height: 200px;
      border-radius: 50%;
      background: linear-gradient(45deg, rgba(55, 88, 249, 0.05), rgba(55, 88, 249, 0.1));
      top: 10%;
      right: -50px;
      z-index: 0;
      animation: float 15s ease-in-out infinite;
    }
  
    .shape {
      position: absolute;
      z-index: 0;
      opacity: 0.15;
    }
  
    .shape-1 {
      width: 120px;
      height: 120px;
      border-radius: 28% 72% 50% 50% / 44% 55% 45% 56%;
      background-color: var(--primary);
      top: 15%;
      left: 10%;
      animation: float 12s ease-in-out infinite;
    }
  
    .shape-2 {
      width: 80px;
      height: 80px;
      border-radius: 37% 63% 51% 49% / 37% 65% 35% 63%;
      background-color: var(--primary-dark);
      bottom: 10%;
      right: 15%;
      animation: float 10s ease-in-out infinite reverse;
    }
  
    .container {
      position: relative;
      max-width: 1200px;
      margin: auto;
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      gap: 3rem;
      z-index: 1;
    }
  
    .content {
      flex: 1;
      min-width: 300px;
    }
  
    h1 {
      font-size: 3rem;
      font-weight: 800;
      line-height: 1.15;
      margin-bottom: 1.75rem;
      background: linear-gradient(to right, var(--text) 30%, var(--primary) 100%);
      background-clip: text;
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      letter-spacing: -0.025em;
    }
  
    /* Highlight key words in heading */
    .highlight {
      position: relative;
      display: inline-block;
    }
  
    .highlight::after {
      content: '';
      position: absolute;
      bottom: 8px;
      left: 0;
      height: 10px;
      width: 100%;
      background-color: rgba(55, 88, 249, 0.2);
      z-index: -1;
      border-radius: 4px;
    }
  
    p {
      max-width: 520px;
      font-size: 1.125rem;
      color: var(--text-light);
      margin-bottom: 2.5rem;
      line-height: 1.7;
    }
  
    /* Fixed typo in the paragraph */
    .typo-fix {
      font-weight: 500;
    }
  
    .buttons {
      display: flex;
      flex-wrap: wrap;
      gap: 1rem;
      margin-bottom: 2rem;
    }
  
    .btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      padding: 0.875rem 1.75rem;
      border-radius: 0.75rem;
      font-size: 1rem;
      font-weight: 600;
      text-decoration: none;
      transition: all var(--transition);
      box-shadow: var(--shadow-sm);
    }
  
    .btn-primary {
      background-color: var(--primary);
      color: white;
      box-shadow: 0 4px 12px rgba(55, 88, 249, 0.25);
    }
  
    .btn-primary:hover {
      background-color: var(--primary-hover);
      transform: translateY(-2px);
      box-shadow: 0 6px 16px rgba(55, 88, 249, 0.35);
    }
  
    .btn-primary:active {
      transform: translateY(0);
      box-shadow: 0 2px 8px rgba(55, 88, 249, 0.2);
    }
  
    .btn-secondary {
      color: var(--text);
      background-color: var(--bg);
      border: 1px solid var(--border);
    }
  
    .btn-secondary:hover {
      background-color: var(--bg-alt);
      transform: translateY(-2px);
      box-shadow: var(--shadow);
    }
  
    .btn-secondary:active {
      transform: translateY(0);
      box-shadow: var(--shadow-sm);
    }
  
    /* Improved icon styling */
    .btn-icon {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      margin-right: 0.5rem;
      font-size: 1.25rem;
    }
  
    .clients {
      margin-top: 3rem;
    }
  
    .clients h6 {
      font-size: 0.85rem;
      font-weight: 600;
      color: var(--text-lighter);
      display: flex;
      align-items: center;
      margin-bottom: 1.5rem;
      text-transform: uppercase;
      letter-spacing: 0.05em;
    }
  
    .clients h6::after {
      content: '';
      flex: 1;
      height: 1px;
      background: linear-gradient(to right, var(--border), transparent);
      margin-left: 1rem;
    }
  
    .brand-logos {
      display: flex;
      gap: 2.5rem;
      flex-wrap: wrap;
      align-items: center;
    }
  
    .brand-logos img {
      height: 28px;
      opacity: 0.7;
      transition: opacity var(--transition), transform var(--transition);
      filter: grayscale(80%);
    }
  
    .brand-logos img:hover {
      opacity: 1;
      transform: scale(1.05);
      filter: grayscale(0%);
    }
  
    .image-section {
      flex: 1;
      position: relative;
      display: flex;
      justify-content: center;
      min-width: 300px;
    }
  
    /* Enhanced image treatment */
    .image-container {
      position: relative;
      width: 100%;
      max-width: 500px;
    }
  
    .image-section img {
      max-width: 100%;
      border-radius: 1.5rem;
      box-shadow: var(--shadow-lg);
      transition: transform var(--transition);
      position: relative;
      z-index: 1;
    }
  
    /* Image decoration elements */
    .image-decoration {
      position: absolute;
      width: 100%;
      height: 100%;
      top: 0;
      left: 0;
      z-index: 0;
      pointer-events: none;
    }
  
    .image-decoration::before {
      content: '';
      position: absolute;
      width: 70%;
      height: 70%;
      border: 2px dashed var(--primary-light);
      border-radius: 1.5rem;
      top: -15px;
      right: -15px;
      z-index: -1;
    }
  
    .image-decoration::after {
      content: '';
      position: absolute;
      width: 80px;
      height: 80px;
      background-color: var(--primary-light);
      border-radius: 1rem;
      bottom: -20px;
      left: -20px;
      z-index: -1;
    }
  
    .dots {
      position: absolute;
      width: 80px;
      height: 80px;
      background-image: radial-gradient(var(--primary) 2px, transparent 2px);
      background-size: 10px 10px;
      top: -30px;
      left: 10%;
      z-index: 0;
      opacity: 0.5;
    }
  
    @keyframes float {
      0% {
        transform: translateY(0px) rotate(0deg);
      }
      50% {
        transform: translateY(-15px) rotate(5deg);
      }
      100% {
        transform: translateY(0px) rotate(0deg);
      }
    }
  
    /* Responsive improvements */
    @media (max-width: 768px) {
      .hero {
        padding: 5rem 1.25rem 4rem;
      }
      
      h1 {
        font-size: 2.5rem;
      }
      
      p {
        font-size: 1rem;
        margin-bottom: 2rem;
      }
      
      .buttons {
        justify-content: flex-start;
      }
      
      .btn {
        padding: 0.75rem 1.5rem;
      }
      
      .clients {
        margin-top: 2.5rem;
      }
      
      .brand-logos {
        justify-content: flex-start;
        gap: 1.5rem;
      }
      
      .image-section {
        margin-top: 1rem;
      }
      
      .dots {
        width: 60px;
        height: 60px;
        left: -1rem;
        bottom: -1rem;
      }
    }
  
    @media (min-width: 769px) and (max-width: 1023px) {
      .container {
        padding: 0 2rem;
      }
      
      .buttons {
        display: flex;
      }
      
      .btn {
        padding: 0.75rem 1.5rem;
      }
    }
  
    @media (min-width: 1024px) {
      .hero {
        padding: 8rem 2rem 7rem;
      }
      
      .container {
        gap: 4rem;
      }
      
      .content {
        flex: 0 0 45%;
      }
      
      .image-section {
        flex: 0 0 45%;
      }
    }
  
    /* For ultra-wide screens */
    @media (min-width: 1440px) {
      .container {
        max-width: 1400px;
      }
      
      h1 {
        font-size: 4rem;
      }
    }
  </style>
  
  <section class="hero">
    <!-- Added decorative shapes -->
    <div class="shape shape-1"></div>
    <div class="shape shape-2"></div>
    
    <div class="container">
      <div class="content">
        <h1>
          The <span class="highlight">Greatest</span><br />
          Journey Of Online<br />
          Payment.
        </h1>
        <p>
          With TailGrids, businesses and students thrive together.
          <span class="typo-fix">Businesses can perfectly match their staffing to changing demand
          throughout the day.</span>
        </p>
        <div class="buttons">
          <a href="/getstarted" class="btn btn-primary">Get Started</a>
          <a href="/download-app" class="btn btn-secondary">
            <span class="btn-icon">
              <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                <path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"></path>
                <polyline points="7 10 12 15 17 10"></polyline>
                <line x1="12" y1="15" x2="12" y2="3"></line>
              </svg>
            </span>
            Download App
          </a>
        </div>
        <div class="clients">
          <h6>Trusted By Leading Companies</h6>
          <div class="brand-logos">
            <img src="https://cdn.tailgrids.com/2.0/image/assets/images/brands/ayroui.svg" alt="AyroUI" />
            <img src="https://cdn.tailgrids.com/2.0/image/assets/images/brands/graygrids.svg" alt="GrayGrids" />
            <img src="https://cdn.tailgrids.com/2.0/image/assets/images/brands/uideck.svg" alt="UIDeck" />
          </div>
        </div>
      </div>
      <div class="image-section">
        <div class="image-container">
          <div class="dots"></div>
          <div class="image-decoration"></div>
          <img src="https://cdn.tailgrids.com/2.0/image/marketing/images/hero/hero-image-01.png" alt="Payment Solution Dashboard" />
        </div>
      </div>
    </div>
  </section>