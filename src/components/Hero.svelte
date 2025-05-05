<!-- Hero.svelte -->
<script lang="ts">
  import { onMount, onDestroy } from 'svelte';
  
  // Props with defaults
  export let title = "Svelte UI Components";
  export let subtitle = "Professional UI components for modern Svelte applications with zero dependencies.";
  export let browseUrl = "#components";
  export let githubUrl = "https://github.com/yourusername/svelte-components";

  let isInView = false;
  let observer: IntersectionObserver;
  
  // Component categories for the code terminal
  const componentCategories = [
    "Form Controls",
    "Data Display",
    "Navigation",
    "Feedback"
  ];

  onMount(() => {
    // Modern approach using Intersection Observer API
    observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          isInView = true;
          observer.disconnect();
          
          // Start the typing animation when in view
          setTimeout(startTypingAnimation, 500);
        }
      });
    }, { threshold: 0.2 });
    
    const heroElement = document.querySelector('.hero');
    if (heroElement) {
      observer.observe(heroElement);
    }
  });

  onDestroy(() => {
    if (observer) {
      observer.disconnect();
    }
  });
  
  // Terminal typing animation
  let terminalText = '';
  let currentLine = 0;
  let currentChar = 0;
  let isTyping = false;
  
  const codeSnippet = [
    'import { Button } from "svelte-ui";',
    '',
    '<Button',
    '  variant="primary"',
    '  size="md"',
    '  on:click={() => console.log("Button clicked!")}',
    '>',
    '  Explore Components',
    '</Button>'
  ];
  
  function startTypingAnimation() {
    isTyping = true;
    typeNextCharacter();
  }
  
  function typeNextCharacter() {
    if (!isTyping) return;
    
    if (currentLine < codeSnippet.length) {
      if (currentChar < codeSnippet[currentLine].length) {
        terminalText += codeSnippet[currentLine][currentChar];
        currentChar++;
        setTimeout(typeNextCharacter, Math.random() * 50 + 20);
      } else {
        terminalText += '\n';
        currentLine++;
        currentChar = 0;
        setTimeout(typeNextCharacter, 200);
      }
    }
  }
</script>

<section class="hero">
  <div class="hero-bg">
    <div class="grid-lines"></div>
    <div class="noise-overlay"></div>
  </div>
  
  <div class="container">
    <div class="content" class:visible={isInView}>
      <div class="tags">
        <span class="tag">TypeScript</span>
        <span class="tag">Svelte</span>
      </div>
      
      <h1>{title}</h1>
      <p>{subtitle}</p>
      
      <div class="actions">
        <a href={browseUrl} class="cta-primary">
          <span class="cta-text">Browse Components</span>
          <span class="cta-icon">
            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <path d="M5 12h14"></path>
              <path d="m12 5 7 7-7 7"></path>
            </svg>
          </span>
        </a>
        <a href={githubUrl} class="cta-secondary">
          <span class="cta-icon">
            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="currentColor">
              <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"></path>
            </svg>
          </span>
          <span class="cta-text">GitHub</span>
        </a>
      </div>
    </div>
    
    <div class="showcase" class:visible={isInView}>
      <div class="code-terminal">
        <div class="terminal-header">
          <div class="terminal-buttons">
            <span class="terminal-button close"></span>
            <span class="terminal-button minimize"></span>
            <span class="terminal-button maximize"></span>
          </div>
          <div class="terminal-title">component-example.svelte</div>
        </div>
        <div class="terminal-body">
          <pre class="terminal-code"><code>{terminalText}</code></pre>
          <div class="cursor" class:blink={isTyping}></div>
        </div>
        
        <div class="floating-tags">
          {#each componentCategories as category, i}
            <div class="floating-tag" style="--delay: {i * 0.2}s; --offset: {i * 5}px;">
              {category}
            </div>
          {/each}
        </div>
      </div>
    </div>
  </div>
  
  <div class="features" class:visible={isInView}>
    <div class="feature">
      <div class="feature-icon">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
          <path d="M14.5 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V7.5L14.5 2z"></path>
          <polyline points="14 2 14 8 20 8"></polyline>
          <path d="M8 13h8"></path>
          <path d="M8 17h8"></path>
          <path d="M8 9h1"></path>
        </svg>
      </div>
      <h3>TypeScript Ready</h3>
      <p>Full type safety with comprehensive TypeScript definitions</p>
    </div>
    
    <div class="feature">
      <div class="feature-icon">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
          <path d="M12 2L2 7l10 5 10-5-10-5z"></path>
          <path d="M2 17l10 5 10-5"></path>
          <path d="M2 12l10 5 10-5"></path>
        </svg>
      </div>
      <h3>Zero Dependencies</h3>
      <p>Lightweight package with no external dependencies</p>
    </div>
    
    <div class="feature">
      <div class="feature-icon">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
          <circle cx="12" cy="12" r="10"></circle>
          <path d="m16 12-4 4-4-4"></path>
          <path d="M12 8v8"></path>
        </svg>
      </div>
      <h3>SSR Compatible</h3>
      <p>Works with SvelteKit and all SSR environments</p>
    </div>
    
    <div class="feature">
      <div class="feature-icon">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
          <path d="M2 12a10 10 0 1 1 20 0 10 10 0 0 1-20 0Z"></path>
          <path d="M12 2a4.4 4.4 0 0 0-4 7 4.4 4.4 0 0 0 0 10 4.4 4.4 0 0 0 8 0 4.4 4.4 0 0 0 0-10 4.4 4.4 0 0 0-4-7Z"></path>
          <path d="M12 2v20"></path>
        </svg>
      </div>
      <h3>Theme System</h3>
      <p>Built-in light and dark themes with custom theme support</p>
    </div>
  </div>
</section>

<style>
  .hero {
    position: relative;
    min-height: 50vh;
    padding: 6rem 2rem;
    display: flex;
    flex-direction: column;
    align-items: center;
    overflow: hidden;
  }
  
  /* White background with subtle grid */
  .hero-bg {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    z-index: -1;
    overflow: hidden;
    background-color: #ffffff;
  }
  
  .grid-lines {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-image: linear-gradient(to right, rgba(230, 235, 240, 0.6) 1px, transparent 1px),
                    linear-gradient(to bottom, rgba(230, 235, 240, 0.6) 1px, transparent 1px);
    background-size: 40px 40px;
  }
  
  .noise-overlay {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.65' numOctaves='3' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.03'/%3E%3C/svg%3E");
    opacity: 0.2;
  }
  
  .container {
    width: 100%;
    max-width: 1400px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 5rem;
    align-items: center;
  }
  
  /* Content area */
  .content {
    display: flex;
    flex-direction: column;
    gap: 1.75rem;
    opacity: 0;
    transform: translateY(1.5rem);
    transition: opacity 0.8s ease, transform 0.8s ease;
  }
  
  .content.visible {
    opacity: 1;
    transform: translateY(0);
  }
  
  .tags {
    display: flex;
    gap: 0.75rem;
  }
  
  .tag {
    display: inline-flex;
    font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
    padding: 0.4rem 1rem;
    border-radius: 100px;
    font-size: 14px;
    font-weight: 500;
    letter-spacing: 0.02em;
    background-color: rgba(37, 99, 235, 0.1);
    color: #2563eb;
  }
  
  .tag:nth-child(2) {
    background-color: rgba(17, 24, 39, 0.1);
    color: #111827;
  }
  
  h1 {
    font-size: 4rem;
    font-weight: 800;
    line-height: 1.1;
    letter-spacing: -0.03em;
    background: linear-gradient(to right, #1e40af, #3b82f6);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    color: transparent;
    margin: 0;
    font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
  }
  
  p {
    font-size: 1.3rem;
    line-height: 1.5;
    color: #64748b;
    margin: 0;
    font-weight: 400;
    font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
  }
  
  .actions {
    display: flex;
    gap: 1rem;
    margin-top: 1rem;
  }
  
  .cta-primary {
    display: inline-flex;
    align-items: center;
    gap: 0.75rem;
    background-color: #2563eb;
    color: white;
    font-weight: 600;
    padding: 0.875rem 1.75rem;
    border-radius: 0.5rem;
    text-decoration: none;
    transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    position: relative;
    overflow: hidden;
    box-shadow: 0 4px 12px rgba(37, 99, 235, 0.25);
  }
  
  .cta-primary:hover {
    background-color: #1d4ed8;
    transform: translateY(-2px);
    box-shadow: 0 6px 20px rgba(37, 99, 235, 0.35);
  }
  
  .cta-primary::after {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    height: 100%;
    background: linear-gradient(to right, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0.2));
    transform: translateX(-100%);
    transition: transform 0.6s cubic-bezier(0.4, 0, 0.2, 1);
  }
  
  .cta-primary:hover::after {
    transform: translateX(100%);
  }
  
  .cta-secondary {
    display: inline-flex;
    align-items: center;
    gap: 0.75rem;
    background-color: rgba(241, 245, 249, 0.8);
    color: #1e293b;
    font-weight: 600;
    padding: 0.875rem 1.75rem;
    border-radius: 0.5rem;
    text-decoration: none;
    transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    border: 1px solid #e2e8f0;
    box-shadow: 0 2px 6px rgba(0, 0, 0, 0.05);
  }
  
  .cta-secondary:hover {
    background-color: #f8fafc;
    transform: translateY(-2px);
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
  }
  
  /* Code terminal showcase */
  .showcase {
    opacity: 0;
    transform: translateX(2rem);
    transition: opacity 0.8s ease 0.2s, transform 0.8s ease 0.2s;
  }
  
  .showcase.visible {
    opacity: 1;
    transform: translateX(0);
  }
  
  .code-terminal {
    position: relative;
    width: 100%;
    aspect-ratio: 16/9;
    background-color: #0f172a;
    border-radius: 0.75rem;
    overflow: hidden;
    box-shadow: 
      0 20px 40px -10px rgba(0, 0, 0, 0.1),
      0 12px 24px -10px rgba(0, 0, 0, 0.1),
      0 0 0 1px rgba(0, 0, 0, 0.05);
  }
  
  .terminal-header {
    display: flex;
    align-items: center;
    padding: 0.75rem 1rem;
    background-color: #1e293b;
    border-bottom: 1px solid #334155;
  }
  
  .terminal-buttons {
    display: flex;
    gap: 0.5rem;
    margin-right: 1rem;
  }
  
  .terminal-button {
    width: 12px;
    height: 12px;
    border-radius: 50%;
  }
  
  .terminal-button.close {
    background-color: #ef4444;
  }
  
  .terminal-button.minimize {
    background-color: #f59e0b;
  }
  
  .terminal-button.maximize {
    background-color: #10b981;
  }
  
  .terminal-title {
    color: #cbd5e1;
    font-size: 0.85rem;
    font-family: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, monospace;
  }
  
  .terminal-body {
    padding: 1.5rem;
    position: relative;
    height: calc(100% - 3.5rem);
    font-family: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, monospace;
  }
  
  .terminal-code {
    margin: 0;
    color: #f1f5f9;
    font-size: 1rem;
    line-height: 1.6;
    white-space: pre-wrap;
  }
  
  .terminal-code :global(.highlight) {
    color: #3b82f6;
  }
  
  .cursor {
    display: inline-block;
    width: 10px;
    height: 1.2rem;
    background-color: #3b82f6;
    position: relative;
    margin-left: 2px;
    vertical-align: middle;
  }
  
  .cursor.blink {
    animation: blink 1s step-end infinite;
  }
  
  @keyframes blink {
    0%, 100% { opacity: 1; }
    50% { opacity: 0; }
  }
  
  /* Floating tags around the terminal */
  .floating-tags {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    z-index: 1;
    pointer-events: none;
  }
  
  .floating-tag {
    position: absolute;
    padding: 0.5rem 1rem;
    border-radius: 100px;
    background-color: rgba(59, 130, 246, 0.15);
    color: #60a5fa;
    font-size: 0.9rem;
    font-weight: 600;
    box-shadow: 0 0 20px rgba(59, 130, 246, 0.1);
    animation: float 10s ease-in-out infinite;
    animation-delay: var(--delay, 0s);
    transform: translateY(var(--offset, 0px));
    white-space: nowrap;
  }
  
  .floating-tag:nth-child(1) {
    top: 20%;
    right: -30px;
    animation-duration: 12s;
  }
  
  .floating-tag:nth-child(2) {
    top: 50%;
    left: -40px;
    animation-duration: 15s;
  }
  
  .floating-tag:nth-child(3) {
    bottom: 30%;
    right: 10%;
    animation-duration: 14s;
  }
  
  .floating-tag:nth-child(4) {
    bottom: 10%;
    left: 25%;
    animation-duration: 13s;
  }
  
  @keyframes float {
    0%, 100% {
      transform: translateY(var(--offset, 0px));
    }
    50% {
      transform: translateY(calc(var(--offset, 0px) - 20px));
    }
  }
  
  /* Features section */
  .features {
    width: 100%;
    max-width: 1400px;
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 2rem;
    margin-top: 7rem;
    opacity: 0;
    transform: translateY(2rem);
    transition: opacity 0.8s ease 0.3s, transform 0.8s ease 0.3s;
  }
  
  .features.visible {
    opacity: 1;
    transform: translateY(0);
  }
  
  .feature {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    padding: 2rem 1.5rem;
    background-color: #ffffff;
    border-radius: 1rem;
    box-shadow: 
      0 10px 25px -5px rgba(0, 0, 0, 0.05),
      0 8px 10px -6px rgba(0, 0, 0, 0.02),
      0 0 0 1px rgba(0, 0, 0, 0.05);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
  }
  
  .feature:hover {
    transform: translateY(-5px);
    box-shadow: 
      0 20px 25px -5px rgba(0, 0, 0, 0.1),
      0 10px 10px -5px rgba(0, 0, 0, 0.04),
      0 0 0 1px rgba(0, 0, 0, 0.1);
  }
  
  .feature-icon {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 3rem;
    height: 3rem;
    border-radius: 0.75rem;
    background: linear-gradient(135deg, #2563eb 0%, #60a5fa 100%);
    color: white;
    margin-bottom: 1.5rem;
    box-shadow: 0 8px 16px -2px rgba(37, 99, 235, 0.25);
  }
  
  .feature-icon svg {
    width: 1.5rem;
    height: 1.5rem;
  }
  
  .feature h3 {
    margin: 0 0 0.75rem 0;
    font-size: 1.2rem;
    font-weight: 600;
    color: #111827;
    letter-spacing: -0.01em;
  }
  
  .feature p {
    margin: 0;
    font-size: 0.95rem;
    color: #64748b;
  }
  
  /* Responsive styles */
  @media (max-width: 1280px) {
    .container {
      gap: 4rem;
    }
    
    h1 {
      font-size: 3.5rem;
    }
  }
  
  @media (max-width: 1024px) {
    .hero {
      padding: 5rem 2rem;
    }
    
    .container {
      grid-template-columns: 1fr;
      gap: 5rem;
    }
    
    .features {
      grid-template-columns: repeat(2, 1fr);
      margin-top: 5rem;
    }
    
    .showcase {
      max-width: 80%;
      margin: 0 auto;
    }
    
    .floating-tag {
      display: none;
    }
  }
  
  @media (max-width: 768px) {
    .hero {
      padding: 4rem 1.5rem;
    }
    
    h1 {
      font-size: 3rem;
    }
    
    .showcase {
      max-width: 100%;
    }
    
    .code-terminal {
      aspect-ratio: 4/3;
    }
  }
  
  @media (max-width: 640px) {
    .actions {
      flex-direction: column;
      width: 100%;
    }
    
    .cta-primary, .cta-secondary {
      width: 100%;
      justify-content: center;
    }
    
    .features {
      grid-template-columns: 1fr;
    }
    
    h1 {
      font-size: 2.5rem;
    }
    
    p {
      font-size: 1.1rem;
    }
    
    .feature {
      padding: 2rem 1.5rem;
    }
  }
</style>