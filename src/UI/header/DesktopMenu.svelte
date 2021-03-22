<script>
  import Button from "../Button.svelte";
  import { fly, fade } from "svelte/transition";
</script>

<nav class="desktop-nav" transition:fly={{ duration: 250, x: 200 }}>
  <div class="desktop-nav__menu">
    <a href="#" transition:fade={{ delay: 200 }}>Pricing</a>
    <a href="#" transition:fade={{ delay: 300 }}>About</a>
    <a href="#" transition:fade={{ delay: 400 }}>Contact</a>
  </div>
  <Button type="primary"/>
</nav>

<style>
    .desktop-nav {
      flex: 1;
      /* padding: 9.5rem 2.4rem; */
      display: flex;
      flex-flow: row nowrap;
      align-items: center;
      justify-content: space-between;
    }
    .desktop-nav__menu {
      height: 100%;
      width: 23.2rem;
      display: flex;
      flex-flow: row nowrap;
      justify-content: space-between;
      align-items: center;
    }
    .desktop-nav__menu a {
      color: var(--medium-blue);
      opacity: 0.7;
    }
    .desktop-nav__menu a:hover {
      opacity: 1;
    }
  </style>
  
