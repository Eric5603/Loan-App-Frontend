<script lang="ts">
    /**
     * Handles newsletter form submission with visual feedback
     * @param {SubmitEvent} event - The form submission event
     */
    function handleSubmit(event: SubmitEvent): void {
      event.preventDefault();
      
      const form = event.target as HTMLFormElement;
      const input = form.querySelector('input[type="email"]') as HTMLInputElement;
      const button = form.querySelector('button') as HTMLButtonElement;
      
      if (!input || !button) return;
      
      // Log submission (replace with actual API call in production)
      console.log('Newsletter subscription:', input.value);
      
      // Store original button state
      const originalText = button.innerHTML;
      
      // Update button with success state
      button.innerHTML = '<span class="check-icon">✓</span> Thanks!';
      button.querySelector('.check-icon')?.classList.add('check-icon');
      button.classList.add('newsletter-container', 'success');
      
      // Reset form after delay
      setTimeout(() => {
        button.innerHTML = originalText;
        button.classList.remove('success');
        input.value = '';
      }, 2000);
    }
  </script>
  
  <div class="footer-container">
    <footer class="modern-footer">
      <div class="footer-content">
        <!-- Brand Column -->
        <div class="brand-column">
          <div class="footer-logo">
            <svg width="40" height="40" viewBox="0 0 40 40" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
              <path d="M20 0C8.95 0 0 8.95 0 20C0 31.05 8.95 40 20 40C31.05 40 40 31.05 40 20C40 8.95 31.05 0 20 0ZM20 30C14.48 30 10 25.52 10 20C10 14.48 14.48 10 20 10C25.52 10 30 14.48 30 20C30 25.52 25.52 30 20 30Z" fill="url(#paint0_linear)"/>
              <defs>
                <linearGradient id="paint0_linear" x1="0" y1="0" x2="40" y2="40" gradientUnits="userSpaceOnUse">
                  <stop stop-color="#00D4FF"/>
                  <stop offset="1" stop-color="#00A3FF"/>
                </linearGradient>
              </defs>
            </svg>
            <span>Horizon</span>
          </div>
          <p class="brand-desc">Empowering digital experiences through innovative design and cutting-edge technology solutions.</p>
          <div class="social-links">
            <!-- Social Media Icons -->
            <a href="https://twitter.com" aria-label="Twitter">
              <svg width="22" height="22" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                <path d="M18 4H22L14 21H10L18 4Z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                <path d="M2 4H6L14 21H10L2 4Z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
              </svg>
            </a>
            <a href="https://facebook.com" aria-label="Facebook">
              <svg width="22" height="22" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                <path d="M18 2H15C13.6739 2 12.4021 2.52678 11.4645 3.46447C10.5268 4.40215 10 5.67392 10 7V10H7V14H10V22H14V14H17L18 10H14V7C14 6.73478 14.1054 6.48043 14.2929 6.29289C14.4804 6.10536 14.7348 6 15 6H18V2Z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
              </svg>
            </a>
            <a href="https://linkedin.com" aria-label="LinkedIn">
              <svg width="22" height="22" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                <path d="M16 8C17.5913 8 19.1174 8.63214 20.2426 9.75736C21.3679 10.8826 22 12.4087 22 14V21H18V14C18 13.4696 17.7893 12.9609 17.4142 12.5858C17.0391 12.2107 16.5304 12 16 12C15.4696 12 14.9609 12.2107 14.5858 12.5858C14.2107 12.9609 14 13.4696 14 14V21H10V14C10 12.4087 10.6321 10.8826 11.7574 9.75736C12.8826 8.63214 14.4087 8 16 8Z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                <path d="M6 9H2V21H6V9Z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                <path d="M4 6C5.10457 6 6 5.10457 6 4C6 2.89543 5.10457 2 4 2C2.89543 2 2 2.89543 2 4C2 5.10457 2.89543 6 4 6Z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
              </svg>
            </a>
            <a href="https://instagram.com" aria-label="Instagram">
              <svg width="22" height="22" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                <path d="M17 2H7C4.23858 2 2 4.23858 2 7V17C2 19.7614 4.23858 22 7 22H17C19.7614 22 22 19.7614 22 17V7C22 4.23858 19.7614 2 17 2Z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                <path d="M16 11.3701C16.1234 12.2023 15.9813 13.0523 15.5938 13.7991C15.2063 14.5459 14.5932 15.1515 13.8416 15.5297C13.0901 15.908 12.2385 16.0397 11.4078 15.906C10.5771 15.7723 9.80976 15.3801 9.21484 14.7852C8.61992 14.1903 8.22773 13.4229 8.09407 12.5923C7.9604 11.7616 8.09207 10.91 8.47033 10.1584C8.84859 9.40691 9.45419 8.79385 10.201 8.40637C10.9478 8.01889 11.7978 7.87665 12.63 8.00006C13.4789 8.12594 14.2649 8.52152 14.8717 9.12836C15.4785 9.73521 15.8741 10.5211 16 11.3701Z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                <path d="M17.5 6.5H17.51" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
              </svg>
            </a>
            <a href="https://github.com" aria-label="GitHub">
              <svg width="22" height="22" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                <path d="M16 22V18.13C16.0375 17.6532 15.9731 17.1738 15.811 16.7238C15.6489 16.2738 15.3929 15.8634 15.06 15.52C18.2 15.17 21.5 13.98 21.5 8.52C21.4997 7.12383 20.9627 5.7812 20 4.77C20.4559 3.54851 20.4236 2.19835 19.91 0.999999C19.91 0.999999 18.73 0.649999 16 2.48C13.708 1.85882 11.292 1.85882 9 2.48C6.27 0.649999 5.09 0.999999 5.09 0.999999C4.57638 2.19835 4.54414 3.54851 5 4.77C4.03013 5.7887 3.49252 7.14346 3.5 8.55C3.5 13.97 6.8 15.16 9.94 15.55C9.611 15.89 9.35726 16.2954 9.19531 16.7399C9.03335 17.1844 8.96681 17.6581 9 18.13V22" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                <path d="M9 18C4.49 20 4 16 2 16" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
              </svg>
            </a>
          </div>
        </div>
  
        <!-- Main Content Grid -->
        <div class="footer-grid">
          <!-- Link Columns -->
          <div class="footer-links">
            <div class="footer-section">
              <h3>Services</h3>
              <ul>
                <li><a href="/branding">Branding</a></li>
                <li><a href="/design">Design</a></li>
                <li><a href="/marketing">Marketing</a></li>
                <li><a href="/advertisement">Advertisement</a></li>
                <li><a href="/development">Development</a></li>
              </ul>
            </div>
            <div class="footer-section">
              <h3>Company</h3>
              <ul>
                <li><a href="/about">About us</a></li>
                <li><a href="/contact">Contact</a></li>
                <li><a href="/jobs">Careers</a></li>
                <li><a href="/press">Press</a></li>
                <li><a href="/blog">Blog</a></li>
              </ul>
            </div>
            <div class="footer-section">
              <h3>Resources</h3>
              <ul>
                <li><a href="/help">Help Center</a></li>
                <li><a href="/partners">Partners</a></li>
                <li><a href="/resources">Resources</a></li>
                <li><a href="/newsletter">Newsletter</a></li>
              </ul>
            </div>
          </div>
  
          <!-- Newsletter Section -->
          <div class="newsletter-container">
            <h3>Join Our Newsletter</h3>
            <p>Get exclusive updates, industry insights, and special offers delivered straight to your inbox.</p>
            <form on:submit={handleSubmit}>
              <div class="input-group">
                <input 
                  type="email" 
                  placeholder="Your email address" 
                  required 
                  aria-label="Email for newsletter"
                />
                <button type="submit">Subscribe</button>
              </div>
              <label class="consent-checkbox">
                <input type="checkbox" required>
                <span class="checkmark"></span>
                <span>I agree to receive emails and accept the <a href="/privacy">Privacy Policy</a></span>
              </label>
            </form>
          </div>
        </div>
      </div>
  
      <!-- Footer Bottom -->
      <div class="footer-bottom">
        <div class="legal-links">
          <a href="/terms">Terms</a>
          <a href="/privacy">Privacy</a>
          <a href="/cookies">Cookies</a>
          <a href="/legal">Legal</a>
        </div>
        <p class="copyright">&copy; 2025 Horizon Inc. All rights reserved.</p>
      </div>
    </footer>
  </div>
  
  <style>
    /**
     * CSS Variables
     * Centralized configuration for easy theming and maintenance
     */
    :root {
      /* Core brand colors */
      --brand-primary: #00d4ff;
      --brand-secondary: #00a3ff;
      --brand-gradient: linear-gradient(135deg, var(--brand-primary) 0%, var(--brand-secondary) 100%);
      
      /* Foundational colors */
      --color-white: #ffffff;
      --color-black: #000000;
      --color-text-primary: #2d3748;
      --color-text-secondary: #4a5568;
      --color-text-muted: #718096;
      
      /* UI component colors */
      --color-border: #e2e8f0;
      --color-border-hover: #cbd5e0;
      --color-bg-subtle: #f7fafc;
      --color-bg-hover: #edf2f7;
      --color-bg-active: #e2e8f0;
      --color-success: #10b981;
      
      /* Effects */
      --shadow-sm: 0 1px 2px 0 rgba(0, 0, 0, 0.05);
      --shadow-md: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
      --shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
      --shadow-focus: 0 0 0 3px rgba(0, 212, 255, 0.4);
      
      /* Typography */
      --font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
      --font-weight-normal: 400;
      --font-weight-medium: 500;
      --font-weight-bold: 600;
      --font-weight-extrabold: 700;
      
      /* Layout */
      --spacing-xs: 0.5rem;   /* 8px */
      --spacing-sm: 0.75rem;  /* 12px */
      --spacing-md: 1rem;     /* 16px */
      --spacing-lg: 1.5rem;   /* 24px */
      --spacing-xl: 2rem;     /* 32px */
      --spacing-2xl: 2.5rem;  /* 40px */
      --spacing-3xl: 3rem;    /* 48px */
      --spacing-4xl: 4rem;    /* 64px */
      
      /* Border radius */
      --radius-sm: 0.25rem;   /* 4px */
      --radius-md: 0.5rem;    /* 8px */
      --radius-lg: 0.75rem;   /* 12px */
      --radius-full: 9999px;
      
      /* Transitions */
      --transition-fast: 150ms ease;
      --transition-normal: 250ms ease;
      --transition-slow: 350ms ease;
      
      /* Z-index layers */
      --z-base: 1;
      --z-above: 10;
      --z-modal: 100;
      --z-toast: 1000;
    }
  
    /**
     * Global styles for the footer component
     */
    .footer-container {
      position: relative;
      background-color: var(--color-white); /* Pure white background */
      padding: var(--spacing-4xl) var(--spacing-xl) var(--spacing-2xl);
      overflow: hidden;
      font-family: var(--font-family);
      color: var(--color-text-primary);
    }
  
    /**
     * Main footer layout with added depth
     */
    .modern-footer {
      position: relative;
      z-index: var(--z-base);
      max-width: 1400px;
      margin: 0 auto;
      min-height: 650px; /* Set minimum height */
      border-radius: var(--radius-lg);
      box-shadow: var(--shadow-sm);
      border: 1px solid var(--color-border);
      padding: var(--spacing-3xl) var(--spacing-2xl) var(--spacing-xl);
    }
  
    /**
     * Content wrapper for better structure
     */
    .footer-content {
      display: grid;
      grid-template-columns: 1fr 3fr;
      gap: var(--spacing-4xl);
      margin-bottom: var(--spacing-3xl);
    }
  
    /**
     * Logo styling and branding column
     */
    .brand-column {
      display: flex;
      flex-direction: column;
      gap: var(--spacing-xl);
    }
  
    .footer-logo {
      display: flex;
      align-items: center;
      gap: var(--spacing-sm);
      font-size: 1.5rem;
      font-weight: var(--font-weight-extrabold);
      color: var(--color-text-primary);
      margin-bottom: var(--spacing-md);
    }
  
    .brand-desc {
      color: var(--color-text-secondary);
      font-size: 1rem;
      line-height: 1.6;
      margin: 0;
    }
  
    /**
     * Social links styling
     */
    .social-links {
      display: flex;
      gap: var(--spacing-md);
      margin-top: var(--spacing-md);
    }
  
    .social-links a {
      display: flex;
      align-items: center;
      justify-content: center;
      width: 42px;
      height: 42px;
      border-radius: var(--radius-full);
      background-color: var(--color-bg-subtle);
      color: var(--color-text-muted);
      transition: all var(--transition-fast);
      border: 1px solid var(--color-border);
    }
  
    .social-links a:hover {
      color: var(--brand-primary);
      background-color: var(--color-bg-hover);
      border-color: var(--color-border-hover);
      transform: translateY(-3px);
      box-shadow: var(--shadow-sm);
    }
  
    /**
     * Main grid layout
     */
    .footer-grid {
      display: grid;
      grid-template-columns: 3fr 2fr;
      gap: var(--spacing-3xl);
    }
  
    /**
     * Link sections
     */
    .footer-links {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: var(--spacing-2xl);
    }
  
    .footer-section h3 {
      margin-top: 0;
      margin-bottom: var(--spacing-lg);
      font-size: 1.15rem;
      font-weight: var(--font-weight-bold);
      color: var(--color-text-primary);
      position: relative;
      padding-bottom: var(--spacing-sm);
    }
  
    .footer-section h3::after {
      content: '';
      position: absolute;
      bottom: 0;
      left: 0;
      width: 32px;
      height: 3px;
      background: var(--brand-gradient);
      border-radius: 2px;
    }
  
    .footer-section ul {
      list-style: none;
      padding: 0;
      margin: 0;
    }
  
    .footer-section li {
      margin: var(--spacing-md) 0;
    }
  
    .footer-section a {
      color: var(--color-text-secondary);
      text-decoration: none;
      position: relative;
      transition: all var(--transition-fast);
      font-size: 1rem;
      display: inline-block;
    }
  
    .footer-section a:hover {
      color: var(--brand-primary);
      transform: translateX(5px);
    }
  
    /**
     * Newsletter section
     */
    .newsletter-container {
      background-color: var(--color-bg-subtle);
      padding: var(--spacing-xl);
      border-radius: var(--radius-md);
      border: 1px solid var(--color-border);
    }
  
    .newsletter-container h3 {
      margin-top: 0;
      margin-bottom: var(--spacing-md);
      font-size: 1.25rem;
      font-weight: var(--font-weight-bold);
      color: var(--color-text-primary);
    }
  
    .newsletter-container p {
      font-size: 1rem;
      color: var(--color-text-secondary);
      margin-bottom: var(--spacing-lg);
      line-height: 1.6;
    }
  
    /**
     * Form styling
     */
    .input-group {
      display: flex;
      margin-bottom: var(--spacing-md);
      position: relative;
      width: 100%;
    }
  
    .newsletter-container input[type="email"] {
      flex: 1;
      padding: var(--spacing-md) var(--spacing-lg);
      border-radius: var(--radius-md) 0 0 var(--radius-md);
      border: 1px solid var(--color-border);
      background-color: var(--color-white);
      color: var(--color-text-primary);
      font-size: 1rem;
      transition: all var(--transition-fast);
    }
  
    .newsletter-container input[type="email"]::placeholder {
      color: var(--color-text-muted);
    }
  
    .newsletter-container input[type="email"]:focus {
      outline: none;
      border-color: var(--brand-primary);
      box-shadow: var(--shadow-focus);
    }
  
    .newsletter-container button {
      padding: var(--spacing-md) var(--spacing-xl);
      border-radius: 0 var(--radius-md) var(--radius-md) 0;
      border: none;
      background: var(--brand-gradient);
      color: var(--color-white);
      font-weight: var(--font-weight-bold);
      cursor: pointer;
      transition: all var(--transition-fast);
      font-size: 1rem;
      white-space: nowrap;
    }
  
    .newsletter-container button:hover {
      box-shadow: var(--shadow-md);
      transform: translateY(-2px);
    }
  
    .newsletter-container button.success {
      background: var(--color-success);
    }
  
    .check-icon {
      display: inline-block;
      margin-right: var(--spacing-xs);
      animation: scaleUp 0.3s ease;
    }
  
    @keyframes scaleUp {
      0% { transform: scale(0); }
      50% { transform: scale(1.2); }
      100% { transform: scale(1); }
    }
  
    /**
     * Checkbox styling
     */
    .consent-checkbox {
      display: flex;
      align-items: flex-start;
      gap: var(--spacing-sm);
      font-size: 0.9rem;
      color: var(--color-text-secondary);
      cursor: pointer;
      position: relative;
      padding-left: var(--spacing-xl);
      user-select: none;
      margin-top: var(--spacing-sm);
    }
  
    .consent-checkbox input {
      position: absolute;
      opacity: 0;
      cursor: pointer;
      height: 0;
      width: 0;
    }
  
    .checkmark {
      position: absolute;
      top: 0;
      left: 0;
      height: 18px;
      width: 18px;
      background-color: var(--color-white);
      border: 1px solid var(--color-border);
      border-radius: var(--radius-sm);
      transition: all var(--transition-fast);
    }
  
    .consent-checkbox:hover input ~ .checkmark {
      background-color: var(--color-bg-hover);
    }
  
    .consent-checkbox input:checked ~ .checkmark {
      background-color: var(--brand-primary);
      border-color: var(--brand-primary);
    }
  
    .checkmark:after {
      content: "";
      position: absolute;
      display: none;
    }
  
    .consent-checkbox input:checked ~ .checkmark:after {
      display: block;
    }
  
    .consent-checkbox .checkmark:after {
      left: 6px;
      top: 2px;
      width: 5px;
      height: 10px;
      border: solid var(--color-white);
      border-width: 0 2px 2px 0;
      transform: rotate(45deg);
    }
  
    .consent-checkbox a {
      color: var(--brand-primary);
      text-decoration: none;
      transition: all var(--transition-fast);
    }
  
    .consent-checkbox a:hover {
      text-decoration: underline;
    }
  
    /**
     * Footer bottom section
     */
    .footer-bottom {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding-top: var(--spacing-xl);
      border-top: 1px solid var(--color-border);
      margin-top: var(--spacing-xl);
    }
  
    .legal-links {
      display: flex;
      gap: var(--spacing-xl);
    }
  
    .legal-links a {
      color: var(--color-text-muted);
      text-decoration: none;
      font-size: 0.9rem;
      transition: color var(--transition-fast);
    }
  
    .legal-links a:hover {
      color: var(--brand-primary);
    }
  
    .copyright {
      color: var(--color-text-muted);
      font-size: 0.9rem;
      margin: 0;
    }
  
    /**
     * Responsive breakpoints
     * Organized from largest to smallest for better maintenance
     */
    @media (max-width: 1200px) {
      .footer-content {
        grid-template-columns: 1fr;
        gap: var(--spacing-2xl);
      }
      
      .brand-column {
        max-width: 600px;
      }
  
      .modern-footer {
        min-height: 800px;
      }
    }
  
    @media (max-width: 992px) {
      .footer-grid {
        grid-template-columns: 1fr;
        gap: var(--spacing-2xl);
      }
      
      .newsletter-container {
        max-width: 650px;
      }
  
      .modern-footer {
        min-height: 850px;
      }
    }
  
    @media (max-width: 768px) {
      .footer-container {
        padding: var(--spacing-3xl) var(--spacing-lg) var(--spacing-xl);
      }
      
      .modern-footer {
        padding: var(--spacing-2xl) var(--spacing-lg) var(--spacing-lg);
        min-height: 900px;
      }
      
      .footer-links {
        grid-template-columns: repeat(2, 1fr);
        gap: var(--spacing-xl);
      }
      
      .footer-bottom {
        flex-direction: column-reverse;
        gap: var(--spacing-lg);
        align-items: flex-start;
      }
      
      .legal-links {
        flex-wrap: wrap;
        gap: var(--spacing-lg);
      }
    }
  
    @media (max-width: 576px) {
      .footer-links {
        grid-template-columns: 1fr;
        gap: var(--spacing-lg);
      }
      
      .input-group {
        flex-direction: column;
        gap: var(--spacing-md);
      }
      
      .newsletter-container input[type="email"] {
        border-radius: var(--radius-md);
      }
      
      .newsletter-container button {
        border-radius: var(--radius-md);
        width: 100%;
      }
      
      .footer-bottom {
        text-align: center;
        align-items: center;
      }
      
      .legal-links {
        justify-content: center;
        width: 100%;
      }
      
      .social-links {
        justify-content: center;
      }
  
      .modern-footer {
        min-height: 1000px;
      }
    }
  </style>