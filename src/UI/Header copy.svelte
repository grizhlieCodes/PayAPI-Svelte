<script>
  let viewWidth, message, size;

  $: breakpoint(viewWidth);

  function breakpoint(vw){
    if(vw > 1110){
            message = `Desktop query successful at ${vw}`
            size = 'desktop'
        } else if (vw > 768){
            message = `Tablet query successful at ${vw}`
            size = 'tablet'
        } else {
            message = `Mobile query successful at ${vw}`
            size = 'mobile'
        }
  }

  let mobileMenu = true;
  $: if (size === 'tablet' || size === 'desktop'){
      mobileMenu = false;
  } else {
      mobileMenu = true
  }



</script>

<svelte:window bind:innerWidth={viewWidth} />

<header>
  <p>{viewWidth}</p>
  <p class={size}>
    {message}
  </p>
</header>

<style>
  p:not(:nth-child(1)) {
    padding: 1rem 2rem;
    font-size: 1.5rem;
    min-width: 250px;
    transition: all 500ms ease-in-out;
    border-radius: 10px;
    text-align: center;
  }
  .mobile {
      background: greenyellow;
  }
  .tablet {
    background: salmon;
  }
  .desktop {
    background: skyblue;
  }
</style>
