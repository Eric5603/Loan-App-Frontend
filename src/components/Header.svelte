<script>

    import { onMount } from 'svelte';

 

    let showMenu = false;

 

    const toggleMenu = () => {

      showMenu = !showMenu;

    };

 

    onMount(() => {

      // No theme functionality here anymore

    });

  </script>

 

  <div class="app">

    <header class="header">

      <div class="container">

        <a href="/" class="logo">

          <img src="https://cdn.tailgrids.com/2.0/image/assets/images/logo/logo-primary.svg" alt="Logo" />

        </a>


        

        <nav class="nav">

          <a href="/">Home</a>

          <a href="/payment">Payment</a>

          <a href="/features">Features</a>

          <a href="/signup" class="signup">Sign Up</a>

        </nav>

 

        <button class="hamburger" on:click={toggleMenu} aria-label="Toggle menu">

          <div class:open={showMenu}></div>

        </button>

      </div>

    </header>

 

    {#if showMenu}

      <div class="mobile-menu">

        <a href="/">Home</a>

        <a href="/payment">Payment</a>

        <a href="/features">Features</a>

        <a href="/login">Login</a>

 

        <hr class="mobile-divider" />

 

        <div class="mobile-actions">

          <a href="/signup" class="signup mobile-signup">Sign Up</a>

        </div>

      </div>

    {/if}

  </div>

 

  <style>

    @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;600&display=swap');

 

    /* Variables */

    :global(html) {

      --bg: #f9fafb;

      --text: #1a1a1a;

      --link: #2563eb;

      --link-hover: #1d4ed8;

      --card-bg: rgba(255, 255, 255, 0.85);

      --shadow: rgba(0, 0, 0, 0.08);

      --primary-bg: #2563eb;

      --primary-hover: #1d4ed8;

      --secondary-text: #6b7280;

      --border-color: #e5e7eb;

    }

 

    :global(body) {

      margin: 0;

      font-family: 'Inter', sans-serif;

      background: var(--bg);

      color: var(--text);

      transition: background .3s, color .3s;

    }

 

    /* Header */

    .header {

      background: var(--card-bg);

      backdrop-filter: blur(12px);

      box-shadow: 0 4px 12px var(--shadow);

      position: sticky;

      top: 0;

      z-index: 100;

      padding: 1rem 1.5rem;

    }

 

    .container {

      max-width: 1200px;

      margin: 0 auto;

      display: flex;

      align-items: center;

      justify-content: space-between;

    }

 

    .logo img {

      height: 40px;

      filter: drop-shadow(0 1px 1px var(--shadow));

    }

 

    /* Desktop Nav */

    .nav {

      display: flex;

      align-items: center;

      gap: 1.5rem;

    }

 

    .nav a {

      position: relative;

      padding: 0.75rem 1rem;

      font-weight: 500;

      color: var(--text);

      text-decoration: none;

      border-radius: 0.375rem; /* Rounded corners */

      transition: background-color 0.2s ease-in-out, color 0.2s ease-in-out;

    }

 

    .nav a:hover {

      background-color: rgba(0, 0, 0, 0.05); /* Subtle hover background */

      color: var(--link-hover);

    }

 

    .signup, .mobile-signup {

    background-color: #2dd4bf; /* Teal */

    color: #0f172a; /* Dark text */

    padding: 0.75rem 1.5rem;

    border-radius: 0.375rem;

    font-weight: 600;

    box-shadow: 0 2px 8px rgba(45, 212, 191, 0.3);

    text-decoration: none;

    transition: background-color 0.2s ease-in-out, transform 0.1s ease-in-out;

  }


  .signup:hover, .mobile-signup:hover {

    background-color: #14b8a6; /* Darker teal */

    transform: translateY(-1px);

  }

 

    /* Hamburger */

    .hamburger {

      display: none;

      background: transparent;

      border: none;

      cursor: pointer;

      z-index: 999;

      padding: 0.5rem;

    }

 

    .hamburger div {

      width: 24px;

      height: 2px;

      background: var(--text);

      position: relative;

      transition: all 0.3s ease-in-out;

    }

 

    .hamburger div::before,

    .hamburger div::after {

      content: '';

      position: absolute;

      width: 24px;

      height: 2px;

      background: var(--text);

      transition: all 0.3s ease-in-out;

    }

 

    .hamburger div::before {

      top: -8px;

    }

 

    .hamburger div::after {

      top: 8px;

    }

 

    .hamburger div.open {

      background: transparent;

    }

 

    .hamburger div.open::before {

      transform: rotate(45deg);

      top: 0;

    }

 

    .hamburger div.open::after {

      transform: rotate(-45deg);

      top: 0;

    }

 

    /* Mobile */

    .mobile-menu {

      display: none;

    }

 

    @media (max-width: 768px) {

      .nav {

        display: none;

      }

 

      .hamburger {

        display: block;

      }

 

      .mobile-menu {

        display: flex;

        flex-direction: column;

        position: fixed;

        top: 0;

        left: 0;

        width: 100%;

        height: 100%;

        padding: 2rem;

        background: var(--card-bg);

        backdrop-filter: blur(16px);

        box-shadow: 0 12px 30px var(--shadow);

        gap: 1.5rem;

        overflow-y: auto;

        animation: slideDown 0.3s ease-out;

        z-index: 50;

      }

 

      .mobile-menu a {

        width: 100%;

        padding: 1rem;

        font-size: 1rem;

        font-weight: 500;

        text-align: left;

        color: var(--text);

        background-color: transparent;

        text-decoration: none;

        border-radius: 0.375rem;

        transition: background-color 0.2s ease-in-out, color 0.2s ease-in-out;

      }

 

      .mobile-menu a:hover {

        background-color: rgba(0, 0, 0, 0.05);

        color: var(--link-hover);

      }

 

      .mobile-divider {

        border: 0;

        border-top: 1px solid var(--border-color);

        margin: 1rem 0;

      }

 

      .mobile-actions {

        display: flex;

        flex-direction: column;

        gap: 1rem;

      }

 

      .mobile-signup {

        background-color: var(--primary-bg);

        color: #fff;

        padding: 1rem 1.5rem;

        border-radius: 0.375rem;

        font-weight: 600;

        box-shadow: 0 2px 8px rgba(37, 99, 235, 0.2);

        text-align: center;

        text-decoration: none;

        transition: background-color 0.2s ease-in-out, transform 0.1s ease-in-out;

      }

 

      .mobile-signup:hover {

        background-color: var(--primary-hover);

        transform: translateY(-1px);

      }

    }

 

    @keyframes slideDown {

      from {

        opacity: 0;

        transform: translateY(-1rem);

      }

 

      to {

        opacity: 1;

        transform: translateY(0);

      }

    }

  </style> 