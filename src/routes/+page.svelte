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
  
    .main-container {
  display: flex;
  flex-direction: column; /* Stack children vertically */
  height: 100vh;
  width: 100vw;
}

.top-sections {
  display: flex;
  flex: 1; /* Takes up available space */
}

.section {
  flex: 1;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 0.5em;
}

/** lol ikr */
.left {
  justify-content: right;
  font-size: x-large;
}

.right {
  justify-content: left;
  font-weight: bold;
  font-size: x-large;
}

.subheading {
  flex: 0 0 300px; /* Set a fixed height for the bottom section */
  flex-direction: column;
  text-align: center;
  display: flex;
  align-items: center;
  justify-content: center;
}

  </style>
  
  <nav>
    <a href="#">Client Login</a>
  </nav>
  
<main class="main-container">
    <div class="top-sections">
        <div class="section left">
            <span>Let us make you a piece of software that</span>
        </div>
        <div class="section right">
            <span id='typed'></span>
        </div>
    </div>
    <div class="subheading">
        <div>You'd be surprised what you can optimise with a custom software solution.</div>
        <div>Cloud or self hosted. Made with ❤️ in Cornwall</div>
    </div>
</main>

  