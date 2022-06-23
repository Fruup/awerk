<script lang="ts">
  import { onMount } from "svelte";
  import Logo from "./lib/Logo.svelte";
  import DiscordLogo from "./lib/DiscordLogo.svelte";

  async function getURL() {
    const files = Object.keys(import.meta.globEager('./assets/*'))
    const i = Math.floor(Math.random() * (files.length - 1));

    url = files[i];
  }

  function handleMouseEnter() {
    if (loadTimer) clearTimeout(loadTimer);
  }

  function handleMouseLeave() {
    if (loadTimer) clearTimeout(loadTimer);
    loadTimer = setTimeout(getURL, 100);
  }

  let loadTimer: number;
  let url: string;
  const href = "https://discord.com/channels/425752052245856256/936026417026727957"

  $: src = url && import(/* @vite-ignore */ url).then((r) => r.default);

  onMount(async () => {
    await getURL();
    await src;
  });
</script>

<a class="topleft" {href} target="_blank">
  <h1>AWK</h1>
</a>

<a class="topright" {href} target="_blank">
  <DiscordLogo fillColor="#eee" />
</a>

<main on:mouseenter={handleMouseEnter} on:mouseleave={handleMouseLeave}>
  <Logo fillColor="rgb(65, 65, 65)" strokeColor="#eee" />

  {#await src then src}
    <img width="150px" height="150px" {src} alt="" />
  {/await}
</main>

<style global>
  body {
    position: relative;

    margin: 0;
    padding: 0;

    width: 100vw;
    height: 100vh;

    background: rgb(65, 65, 65);

    display: grid;
    place-items: center;

    overflow: clip;
  }

  .topleft {
    position: absolute;
    margin: 20px 30px;
    top: 0;
    left: 0;
    color: #eee;
  }

  h1 {
    font-family: monospace;
    font-size: 4rem;
    margin: 0;
  }

  .topright {
    position: absolute;

    right: 0;
    top: 0;

    margin: 20px;
  }

  main {
    --max-size: 50vmin;
  }

  main {
    display: grid;
    place-items: center;

    width: var(--max-size);
    height: var(--max-size);
  }

  main:hover img {
    transform: rotateZ(-30deg) translate(-100%, -100%) scale(1);
  }

  div.henlo {
    position: absolute;

    left: 50%;
    top: 50%;

    z-index: 150;
  }

  img {
    position: absolute;

    left: 50%;
    top: 50%;

    transform: translate(-50%, -50%) scale(0.1);

    transition: all 200ms ease-out;

    z-index: 150;
  }

  :root {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
      Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  }
</style>
