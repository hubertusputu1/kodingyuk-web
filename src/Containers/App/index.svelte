<script>
  import { onMount } from "svelte";
  import { flip } from "svelte/animate";
  import { fade, fly } from "svelte/transition";

  import Logo from "../components/Logo.svelte";

  let visible = false;

  onMount(() => {
    setTimeout(() => {
      visible = true;
    }, 1200);
  });

  function typewriter(node, { speed = 300 }) {
    const valid =
      node.childNodes.length === 1 && node.childNodes[0].nodeType === 3;

    if (!valid) {
      throw new Error(
        `This transition only works on elements with a single text node child`
      );
    }

    const text = node.textContent;
    const duration = text.length * speed;

    return {
      duration,
      tick: t => {
        const i = ~~(text.length * t);
        node.textContent = text.slice(0, i);
      }
    };
  }

  function handleClick() {
    window.open("https://www.instagram.com/kodingyuk");
  }
</script>

<style>
  section {
    background-color: #000000;
    height: 100%;
    width: 100%;
    padding: 30;
    display: grid;
    align-content: center;
    align-items: center;
    justify-content: center;
    justify-items: center;
  }

  button {
    font-family: "Roboto";
    font-size: 24px;
    color: #0aa7ff;
    font-weight: bold;
    background-color: unset;
    border: unset;
    cursor: pointer;
  }
</style>

{#if visible}
  <section>
    <Logo {visible} {handleClick} />
    <button in:typewriter on:click={handleClick}>COMING SOON!</button>
  </section>
{/if}
