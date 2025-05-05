<script lang="ts">
    import { writable } from 'svelte/store';
    import { onMount } from 'svelte';
    
    const isMenuOpen = writable(false);
    const toggleMenu = () => isMenuOpen.update(open => !open);
    
    // Close menu when clicking outside
    onMount(() => {
      const handleClickOutside = (event: MouseEvent) => {
        const navbar = document.querySelector('.navbar');
        if (navbar && !navbar.contains(event.target as Node) && $isMenuOpen) {
          isMenuOpen.set(false);
        }
      };
      
      document.addEventListener('click', handleClickOutside);
      
      return () => {
        document.removeEventListener('click', handleClickOutside);
      };
    });
  </script>
  
  <header class="header">
    <div class="container">
      <nav class="navbar">
        <div class="logo">
          <span class="logo-icon">⬢</span>
          <span class="logo-text">Svelte UI</span>
        </div>
        
        <button class="menu-toggle" on:click={toggleMenu} aria-label="Toggle menu">
          <span class="hamburger"></span>
        </button>
        
        {#if $isMenuOpen}
          <button class="mobile-overlay" on:click={toggleMenu} on:keydown={(e) => e.key === 'Enter' && toggleMenu()} aria-label="Close menu"></button>
        {/if}
        
        <div class="nav-container" class:show={$isMenuOpen}>
          <div class="mobile-header">
            <div class="logo mobile-logo">
              <span class="logo-icon">⬢</span>
              <span class="logo-text">Svelte UI</span>
            </div>
            <button class="close-menu" on:click={toggleMenu} aria-label="Close menu">
              <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                <line x1="18" y1="6" x2="6" y2="18"></line>
                <line x1="6" y1="6" x2="18" y2="18"></line>
              </svg>
            </button>
          </div>
          <ul class="nav-menu">
            <li><a href="/" class="active">Home</a></li>
            <li><a href="/playground">Playground</a></li>
            <li><a href="/components">Components</a></li>
            <li><a href="/docs">Documentation</a></li>
            <li><a href="/blogs">Portfolio</a></li>
            <li><a href="/join/discord">Join us on Discord</a></li>
          </ul>
          
          <div class="auth-links">
            <a href="/getstarted" class="get-started">Donate</a>
          </div>
        </div>
      </nav>
    </div>
  </header>
  
  <style>
    :global(body) {
      margin: 0;
      font-family: 'Inter', system-ui, sans-serif;
      font-size: 16px;
      line-height: 1.5;
      color: #e0e0e0;
      background-color: #212020;
    }
    
    .header {
      background: #121212;
      position: sticky;
      top: 0;
      z-index: 1000;
      box-shadow: 0 4px 20px rgba(0, 0, 0, 0.3);
    }
    
    .container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 0 1.5rem;
    }
    
    .navbar {
      display: flex;
      align-items: center;
      justify-content: space-between;
      height: 70px;
      position: relative;
    }
    
    .logo {
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }
    
    .logo-icon {
      color: #ff6b35;
      font-size: 1.75rem;
      filter: drop-shadow(0 0 8px rgba(255, 107, 53, 0.4));
    }
    
    .logo-text {
      color: white;
      font-size: 1.25rem;
      font-weight: 700;
      letter-spacing: 0.5px;
    }
    
    .nav-container {
      display: flex;
      align-items: center;
      gap: 2rem;
    }
    
    .nav-menu {
      display: flex;
      list-style: none;
      gap: 1.5rem;
      margin: 0;
      padding: 0;
    }
    
    .nav-menu li a {
      color: #b0b0b0;
      text-decoration: none;
      font-size: 1rem;
      font-weight: 500;
      position: relative;
      padding: 0.5rem;
      transition: color 0.3s ease;
    }
    
    .nav-menu li a:hover,
    .nav-menu li a.active {
      color: #ff6b35;
    }
    
    .nav-menu li a::after {
      content: '';
      position: absolute;
      left: 0;
      bottom: -4px;
      height: 2px;
      width: 0;
      background-color: #ff6b35;
      transition: width 0.3s ease;
    }
    
    .nav-menu li a:hover::after,
    .nav-menu li a.active::after {
      width: 100%;
    }
    
    .auth-links {
      display: flex;
      align-items: center;
    }
    
    .get-started {
      background-color: #ff6b35;
      color: white;
      border-radius: 8px;
      padding: 0.5rem 1.2rem;
      font-weight: 600;
      text-decoration: none;
      transition: all 0.3s ease;
      box-shadow: 0 4px 12px rgba(255, 107, 53, 0.3);
    }
    
    .get-started:hover {
      background-color: #ff5722;
      transform: translateY(-2px);
      box-shadow: 0 6px 16px rgba(255, 107, 53, 0.4);
    }
    
    .menu-toggle {
      display: none;
      background: transparent;
      border: none;
      cursor: pointer;
      position: relative;
      width: 30px;
      height: 24px;
      padding: 0;
    }
    
    .hamburger {
      position: relative;
      width: 100%;
      height: 2px;
      background-color: white;
      display: block;
      transition: all 0.3s ease;
    }
    
    .hamburger::before,
    .hamburger::after {
      content: '';
      position: absolute;
      width: 100%;
      height: 2px;
      background-color: white;
      left: 0;
      transition: all 0.3s ease;
    }
    
    .hamburger::before {
      top: -8px;
    }
    
    .hamburger::after {
      bottom: -8px;
    }
    
    /* Responsive Styles */
    .mobile-overlay {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-color: rgba(0, 0, 0, 0.7);
      backdrop-filter: blur(4px);
      z-index: 1000;
      border: none;
      cursor: pointer;
    }
    
    .mobile-header {
      display: none;
      width: 100%;
      padding: 1rem;
      border-bottom: 1px solid rgba(255, 255, 255, 0.1);
      margin-bottom: 1.5rem;
    }
    
    .mobile-logo {
      margin: 0;
    }
  
    .close-menu {
      display: none;
      background: transparent;
      border: none;
      cursor: pointer;
      color: white;
      padding: 0.5rem;
      transition: transform 0.3s ease;
      border-radius: 50%;
    }
    
    .close-menu:hover {
      background-color: rgba(255, 255, 255, 0.1);
      transform: rotate(90deg);
    }
      
    @media (max-width: 768px) {
      .menu-toggle {
        display: block;
        z-index: 1100;
      }
      
      .mobile-header {
        display: flex;
        justify-content: space-between;
        align-items: center;
      }
      
      .close-menu {
        display: flex;
        margin-right: 3rem;
      }
      
      .navbar {
        height: 60px;
      }
      
      .nav-container {
        position: fixed;
        top: 0;
        right: -100%;
        width: 80%;
        max-width: 320px;
        height: 100vh;
        background: #181818;
        flex-direction: column;
        justify-content: flex-start;
        align-items: flex-start;
        padding: 0;
        transition: right 0.3s cubic-bezier(0.16, 1, 0.3, 1);
        z-index: 1100;
        overflow-y: auto;
      }
      
      .nav-container.show {
        right: 0;
        box-shadow: -10px 0 30px rgba(0, 0, 0, 0.4);
      }
      
      .nav-menu {
        flex-direction: column;
        align-items: flex-start;
        padding: 1rem 1.5rem;
        width: 100%;
        box-sizing: border-box;
      }
      
      .nav-menu li {
        width: 100%;
        margin: 0;
        padding: 0;
      }
      
      .nav-menu li a {
        font-size: 1.125rem;
        padding: 1rem 0;
        display: block;
        width: 100%;
        border-bottom: 1px solid rgba(255, 255, 255, 0.05);
      }
      
      .nav-menu li:last-child a {
        border-bottom: none;
      }
      
      .auth-links {
        width: 100%;
        padding: 1rem 1.5rem 2rem;
        box-sizing: border-box;
      }
      
      .get-started {
        display: block;
        width: 100%;
        text-align: center;
        padding: 0.8rem;
        font-size: 1rem;
        margin-top: 1rem;
      }
    }
  </style>