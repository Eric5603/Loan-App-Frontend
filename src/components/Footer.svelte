<!-- Footer.svelte -->
<script>
    // No JS needed unless adding dynamic logic
  </script>
  
  <footer class="footer">
    <div class="footer-inner">
      <!-- Logo Section -->
      <div class="footer-brand">
        <span class="logo-icon">⬢</span>
        <span class="logo-text">Svelte UI</span>
      </div>
  
      <!-- Navigation Links -->
      <nav class="footer-nav">
        <a href="/">Components</a>
        <a href="/sponsor-us">Sponsor Us</a>
      </nav>
  
      <!-- Social Icons -->
      <div class="footer-socials">
        <a href="/" aria-label="Facebook">
          <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="currentColor">
            <path d="M9.101 23.691v-7.98H6.627v-3.667h2.474v-1.58c0-4.085 1.848-5.978 5.858-5.978.401 0 .955.042 1.468.103a8.68 8.68 0 0 1 1.141.195v3.325a8.623 8.623 0 0 0-.653-.036 26.805 26.805 0 0 0-.733-.009c-.707 0-1.259.096-1.675.309a1.686 1.686 0 0 0-.679.622c-.258.42-.374.995-.374 1.752v1.297h3.919l-.386 2.103-.287 1.564h-3.246v8.286C19.396 23.238 24 18.179 24 12.044c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.628 3.874 10.35 9.101 11.647Z"/>
          </svg>
        </a>
        <a href="/" aria-label="Twitter">
          <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="currentColor">
            <path d="M18.901 1.153h3.68l-8.04 9.19L24 22.846h-7.406l-5.8-7.584-6.638 7.584H.474l8.6-9.83L0 1.154h7.594l5.243 6.932ZM17.61 20.644h2.039L6.486 3.24H4.298Z"/>
          </svg>
        </a>
        <a href="/" aria-label="Instagram">
          <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="currentColor">
            <path d="M12 0C8.74 0 8.333.015 7.053.072 5.775.132 4.905.333 4.14.63c-.789.306-1.459.717-2.126 1.384S.935 3.35.63 4.14C.333 4.905.131 5.775.072 7.053.012 8.333 0 8.74 0 12s.015 3.667.072 4.947c.06 1.277.261 2.148.558 2.913a5.885 5.885 0 0 0 1.384 2.126A5.868 5.868 0 0 0 4.14 23.37c.766.296 1.636.499 2.913.558C8.333 23.988 8.74 24 12 24s3.667-.015 4.947-.072c1.277-.06 2.148-.262 2.913-.558a5.898 5.898 0 0 0 2.126-1.384 5.86 5.86 0 0 0 1.384-2.126c.296-.765.499-1.636.558-2.913.06-1.28.072-1.687.072-4.947s-.015-3.667-.072-4.947c-.06-1.277-.262-2.149-.558-2.913a5.89 5.89 0 0 0-1.384-2.126A5.847 5.847 0 0 0 19.86.63c-.765-.297-1.636-.499-2.913-.558C15.667.012 15.26 0 12 0zm0 2.16c3.203 0 3.585.016 4.85.071 1.17.055 1.805.249 2.227.415.562.217.96.477 1.382.896.419.42.679.819.896 1.381.164.422.36 1.057.413 2.227.057 1.266.07 1.646.07 4.85s-.015 3.585-.074 4.85c-.061 1.17-.256 1.805-.421 2.227a3.81 3.81 0 0 1-.899 1.382 3.744 3.744 0 0 1-1.38.896c-.42.164-1.065.36-2.235.413-1.274.057-1.649.07-4.859.07-3.211 0-3.586-.015-4.859-.074-1.171-.061-1.816-.256-2.236-.421a3.716 3.716 0 0 1-1.379-.899 3.644 3.644 0 0 1-.9-1.38c-.165-.42-.359-1.065-.42-2.235-.045-1.26-.061-1.649-.061-4.844 0-3.196.016-3.586.061-4.861.061-1.17.255-1.814.42-2.234.21-.57.479-.96.9-1.381.419-.419.81-.689 1.379-.898.42-.166 1.051-.361 2.221-.421 1.275-.045 1.65-.06 4.859-.06l.045.03zm0 3.678a6.162 6.162 0 1 0 0 12.324 6.162 6.162 0 1 0 0-12.324zM12 16c-2.21 0-4-1.79-4-4s1.79-4 4-4 4 1.79 4 4-1.79 4-4 4zm7.846-10.405a1.441 1.441 0 0 1-2.88 0 1.44 1.44 0 0 1 2.88 0z"/>
          </svg>
        </a>
        <a href="/" aria-label="LinkedIn">
          <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="currentColor">
            <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 0 1-2.063-2.065 2.064 2.064 0 1 1 2.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
          </svg>
        </a>
      </div>
  
      <!-- Footer Bottom -->
      <div class="footer-copy">
        &copy; 2025 Svelte UI. All rights reserved.
      </div>
    </div>
  </footer>
  
  <style>
    .footer {
      background-color: #1a1a1a;
      color: #e0e0e0;
      padding: 4rem 1rem;
      font-family: 'Inter', system-ui, sans-serif;
    }
  
    .footer-inner {
      max-width: 1200px;
      margin: auto;
      display: grid;
      grid-template-columns: 1fr;
      gap: 2rem;
      text-align: center;
    }
  
    .footer-brand {
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 0.75rem;
    }
  
    .logo-icon {
      font-size: 2rem;
      color: #ff6b35;
    }
  
    .logo-text {
      font-size: 1.5rem;
      font-weight: 700;
      color: #ffffff;
    }
  
    .footer-nav {
      display: flex;
      justify-content: center;
      gap: 2rem;
      flex-wrap: wrap;
    }
  
    .footer-nav a {
      color: #b0b0b0;
      text-decoration: none;
      font-weight: 500;
      position: relative;
      transition: color 0.3s;
    }
  
    .footer-nav a::after {
      content: "";
      position: absolute;
      height: 2px;
      width: 0;
      left: 50%;
      bottom: -4px;
      background: #ff6b35;
      transition: width 0.3s ease, left 0.3s ease;
      transform: translateX(-50%);
    }
  
    .footer-nav a:hover {
      color: #ff6b35;
    }
  
    .footer-nav a:hover::after {
      width: 100%;
    }
  
    .footer-socials {
      display: flex;
      justify-content: center;
      gap: 1.5rem;
    }
  
    .footer-socials a {
      width: 42px;
      height: 42px;
      background: rgba(255, 255, 255, 0.1);
      border-radius: 50%;
      display: grid;
      place-items: center;
      color: #b0b0b0;
      transition: all 0.3s ease;
    }
  
    .footer-socials a:hover {
      background: #ff6b35;
      color: #ffffff;
      transform: translateY(-3px);
      box-shadow: 0 5px 15px rgba(255, 107, 53, 0.4);
    }
  
    .footer-copy {
      font-size: 0.875rem;
      color: #777;
      margin-top: 1rem;
    }
  
    @media (min-width: 768px) {
      .footer-inner {
        grid-template-columns: 1fr 1fr 1fr;
        text-align: left;
        align-items: center;
      }
  
      .footer-brand {
        justify-content: flex-start;
      }
  
      .footer-socials {
        justify-content: flex-end;
      }
  
      .footer-copy {
        grid-column: span 3;
        text-align: center;
        margin-top: 2rem;
        padding-top: 2rem;
        border-top: 1px solid rgba(255, 255, 255, 0.1);
      }
    }
  </style>