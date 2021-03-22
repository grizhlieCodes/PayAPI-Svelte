<script>
  //   import Button from "./Button.svelte";
    import { fly, fade } from "svelte/transition";
  import MobileNav from "./header/MobileMenu.svelte";
  import DesktopMenu from "./header/DesktopMenu.svelte";

  let viewWidth,  size;

  $: breakpoint(viewWidth);

  function breakpoint(vw) {
    if (vw > 1110) {
      size = "desktop";
    } else if (vw > 768) {
      size = "tablet";
    } else {
      size = "mobile";
    }
  }

  let mobileMenu = true;
  $: if (size === "tablet" || size === "desktop") {
    mobileMenu = false;
  } else {
    mobileMenu = true;
  }

  let menuActive = false;

  const activateMenu = () => {
    menuActive = !menuActive;
  };
</script>

<svelte:window bind:innerWidth={viewWidth} />

<header>
  <div class="logo-container">
    <img src="assets/shared/desktop/logo.svg" alt="logo of pay api" transition:fade={{duration: 500, x: 200}}/>
  </div>
  {#if mobileMenu}
    <div id="menu-button" on:click={activateMenu}>
      <div class="menu-button__div" class:active={menuActive} />
      <div class="menu-button__div" class:active={menuActive} />
      <div class="menu-button__div" class:active={menuActive} />
    </div>
    {#if menuActive}
      <MobileNav />
    {/if}
  {:else}
    <DesktopMenu />
  {/if}
</header>

<style>
  header {
    height: 11rem;
    display: flex;
    flex-flow: row nowrap;
    justify-content: space-between;
    align-items: center;
  }
  .logo-container{margin-right: 6.4rem;}
  #menu-button {
    width: 2.8rem;
    height: 100%;
    display: flex;
    flex-flow: column wrap;
    justify-content: center;
    cursor: pointer;
    z-index: 50;
  }
  .menu-button__div {
    width: 100%;
    height: 0.3rem;
    color: var(--medium-blue);
    background: var(--medium-blue);
    user-select: none;
    transform: none;
    transform-origin: 4px 1px;
    transition: 250ms all ease-in-out;
  }
  .menu-button__div:not(:nth-last-child(1)) {
    margin-bottom: 0.4rem;
  }
  .menu-button__div.active {
    background: var(--white);
  }
  .menu-button__div.active:nth-child(1) {
    transform: rotate(45deg);
  }
  .menu-button__div.active:nth-child(2) {
    transform: scaleX(0.1);
    opacity: 0;
  }
  .menu-button__div.active:nth-child(3) {
    transform: rotate(-45deg);
  }
</style>
