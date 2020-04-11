<script>
  import { fade, fly } from "svelte/transition";
  export let visible;

  export let handleClick;
</script>

<style>
  svg {
    cursor: pointer;
  }
</style>

{#if visible}
  <svg
    on:click={handleClick}
    in:fly={{ y: -200, duration: 1500 }}
    out:fade
    width="237"
    height="237"
    fill="none"
    xmlns="http://www.w3.org/2000/svg">
    <circle cx="118.5" cy="118.5" r="118.5" fill="#000" />
    <rect
      x="88.707"
      y="65.276"
      width="17.762"
      height="106.449"
      rx="8.881"
      fill="#0AA7FF" />
    <rect
      x="158.177"
      y="65.275"
      width="17.854"
      height="62.578"
      rx="8.927"
      transform="rotate(51.159 158.177 65.275)"
      fill="#0AA7FF" />
    <rect
      width="17.854"
      height="62.578"
      rx="8.927"
      transform="scale(1 -1) rotate(51.159 258.371 79.404)"
      fill="#0AA7FF" />
  </svg>
{/if}
