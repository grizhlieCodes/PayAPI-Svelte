<script>
  import Button from "../Button.svelte";
  import { fly, fade } from "svelte/transition";

  //TODO: we will need to dispatch a custom event on link clicks

    


</script>

<nav class="mobile-nav" transition:fly={{ duration: 250, x: 200 }}>
  <span class="mobile-nav__divider" />
  <div class="mobile-nav__menu">
    <a href="#" transition:fade={{ delay: 200 }}>Pricing</a>
    <a href="#" transition:fade={{ delay: 300 }}>About</a>
    <a href="#" transition:fade={{ delay: 400 }}>Contact</a>
  </div>
  <Button type="primary" />
</nav>

<style>
  .mobile-nav {
    width: 30rem;
    position: fixed;
    top: 0;
    bottom: 0;
    right: 0;
    background: var(--dark-blue);
    padding: 9.5rem 2.4rem;
    display: flex;
    flex-flow: column wrap;
    justify-content: flex-start;
    align-items: center;
  }
  .mobile-nav__divider {
    width: 100%;
    height: 0.01rem;
    background: #979797;
    opacity: 0.15;
    margin-bottom: 4.3rem;
  }
  .mobile-nav__menu {
    height: 13.6rem;
    display: flex;
    flex-flow: column wrap;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 3.2rem;
  }
  .mobile-nav__menu a {
    color: var(--white);
    opacity: 0.7;
  }
  .mobile-nav__menu a:hover {
    opacity: 1;
  }
</style>
