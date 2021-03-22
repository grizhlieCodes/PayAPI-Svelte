<script>
  import {fade, fly} from "svelte/transition";

  export let customWidth = 'default'
  export let type = "primary";
  export let content = "Schedule a Demo";
</script>

<button class={type} transition:fly={{duration: 400, x: 200}}>
  {content}
</button>

<style>
  button {
    cursor: pointer;
    height: 4.8rem;
    min-width: 17.3rem;
    font-size: 1.5rem;
    /* padding: 1.6rem 2.6rem; */
    font-family: var(--sans-font);
    font-weight: 600;
    border-radius: 2.4rem;
  }
  button:disabled {
    opacity: 50%;
  }
  button:not(.primary) {
    padding: 1.6rem 3.2rem;
  }
  button.primary {
    background: var(--dark-pink);
    color: var(--white);
    width: 100%;
    max-width: 32.7rem;
  }
  @media screen and (min-width: 768px) {
    button.primary {
      width: 17.3rem;
    }
  }
  button.primary:hover:not(:disabled) {
    background: var(--light-pink);
  }
  button.secondary.light {
    background: var(--dark-blue);
    color: var(--white);
    border: 1px solid var(--white);
    width: 12.9rem;
  }
  button.secondary.light:hover:not(:disabled) {
    background: var(--white);
    color: var(--dark-blue);
    font-weight: 700;
  }
  button.secondary.dark {
    background: var(--white);
    color: var(--dark-blue);
    border: 1px solid var(--dark-blue);
    width: 16.8rem;
  }
  button.secondary.dark:hover:not(:disabled) {
    background: var(--medium-blue);
    color: var(--white);
    font-weight: 700;
  }
</style>
