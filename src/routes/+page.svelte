<script lang="ts">
    import { onMount } from 'svelte';
    import Typed from 'typed.js';
  
    let typedInstance: any;

    onMount(() => {
        // Initialize the Typed.js instance
        typedInstance = new Typed('#typed', {
            strings: [
                "reduces your resource waste.",
                "improves inter team collaboration.",
                "streamlines your processes.",
            ],
            typeSpeed: 50,
            backSpeed: 30,
            backDelay: 1000,
            startDelay: 500,
            loop: true,
        });
    });

    // Cleanup Typed instance on component destruction
    import { onDestroy } from 'svelte';
    onDestroy(() => {
    if (typedInstance) {
        typedInstance.destroy(); // Clean up Typed.js instance to avoid memory leaks
    }
    });
  </script>
  
  <style>
    /* Global styles */
    :global(body) {
      margin: 0;
      font-family: 'Courier New', Courier, monospace;
      background: white;
      color: black;
    }
  
    nav {
      position: fixed;
      top: 0;
      width: 100%;
      background: white;
      padding: 1rem;
      box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
      z-index: 1000;
    }
  
    nav a {
      text-decoration: none;
      color: black;
      font-weight: bold;
    }
  
    .main-content {
        display: flex;
        align-items: center;
        justify-content: center;
        font-size: 2rem;
        height: 100vh;
    }

    .section {
        flex: 1;
        display: flex;
        align-items: center;
        justify-content: center;
    }

  
    /* Keyframes to fade text in and out */
    @keyframes fade {
      0% {
        opacity: 0;
      }
      100% {
        opacity: 1;
      }
    }
  </style>
  
  <nav>
    <a href="#">Client Login</a>
  </nav>
  
  <main>
    <div class="main-content" id="fullpage">
        <div class="section">
            <span>Let us make you some software that</span>
        </div>
        <div class="section">
            <span id='typed'></span>
        </div>
    </div>
  </main>
  