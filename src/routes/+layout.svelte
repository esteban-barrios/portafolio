<script lang="ts">
  import "$lib/global.css";
  import { innerWidth } from "svelte/reactivity/window";
  import { slide } from "svelte/transition";

  let sections = ["home", "experience", "skills", "projects", "contact"];
  let isMobile = $state((innerWidth.current ?? 0) < 768);
  let showSections = $state(false);
  let { children } = $props();
  
  $effect(() => {
    isMobile = (innerWidth.current ?? 0) < 768;
    showSections = !isMobile;
  });
</script>

<div class="wrapper">
  <nav>
    <h1>Esteban</h1>
    {#if isMobile}
      <label>
        <input type="checkbox" bind:checked={showSections} />
        {#if showSections}
          <i class="fas fa-times"></i>
        {:else}
          <i class="fas fa-bars"></i>
        {/if}
      </label>
    {:else}
      <ul>
        {#each sections as section, i}
          <li class="link-button">
            <a href="#section-{i}">{section}</a>
          </li>
        {/each}
      </ul>
    {/if}
  </nav>
  {#if showSections && isMobile}
    <ul class="mobile-menu">
      {#each sections as section, i}
        <div class="border-bottom" transition:slide|global>
          <li class="link-button">
            <a href="#section-{i}">{section}</a>
          </li>
        </div>
      {/each}
    </ul>
  {/if}
  <main>
    {@render children()}
  </main>
</div>

<style>
  .wrapper {
    height: 100dvh;
    width: 100%;
    width: -webkit-fill-available;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    align-content: flex-start;
    justify-content: center;
    overflow-y: scroll;
  }
  nav {
    position: fixed;
    top: 0;
    width: 90%;
    height: 4rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    text-align: left;
  }
  main {
    width: 100%;
  }

  .mobile-menu {
    width: 100%;
    position: fixed;
    top: 4rem;
  }
  .border-bottom {
    padding: 0.5rem 1rem;
    border-top: 1px solid #eee;
  }
  input[type="checkbox"] {
    display: none;
  }
  .fas {
    font-size: 24px;
  }
  .link-button {
    text-transform: uppercase;
    font-size: 20px;
  }
  .active {
    font-weight: bold;
    color: red;
  }
  @media (min-width: 768px) {
    nav {
      position: fixed;
      top: 0;
      left: 0;
      width: 15%;
      height: 100dvh;
      flex-direction: column;
      justify-content: start;
      align-items: start;
    }
    main {
      width: 85%;
      height: 100dvh;
      margin-left: 15%;
    }
  }
</style>
