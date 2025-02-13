<script lang="ts">
  import "$lib/global.css";
  import { innerWidth } from 'svelte/reactivity/window';
  import { slide } from 'svelte/transition';
  import {sections} from './shared';
  let { children } = $props();

  
  let isMobile = $state( (innerWidth.current?? 0) < 768 );
  let showSections = $state(false);

  $effect(() => {
    isMobile = (innerWidth.current?? 0) < 768;
    showSections = !isMobile
  });

  function scrollToSection(id: string){
    document.getElementById(id)?.scrollIntoView({behavior: "smooth"});
  }
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
        {#if showSections}
        <ul class="mobile-menu">
          {#each sections.list as section,i}
            <div class="border-bottom" transition:slide|global>
              <li class="link-button">
                <button onclick={() => scrollToSection(`section-${i}`)}>{section}</button>
              </li>
            </div>
          {/each}
        </ul>
        {/if}
      {:else}
      <ul>
        {#each sections.list as section,i}
          <li class="link-button">
            <button onclick={() => scrollToSection(`section-${i}`)}>{section}</button>
          </li>
        {/each}
      </ul>
      {/if}
  </nav>
  <main>
    {@render children()}
  </main>
</div>

<style>
  .wrapper {
    height: 100dvh;
    width: 100dvw;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    align-content: flex-start;
  }
  nav {
    position: fixed; 
    top: 0;
    left: 0;
    width: 100%;
    height: max-content;
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    text-align: left;
    box-shadow: 2px 0 5px rgba(0, 0, 0, 0.1);
    border-bottom: none;
  }
  main {
    width: 100%;
  }

  .mobile-menu{
    width: 100%;
  }
  .border-bottom {
    padding: 0.5em 0;
    border-top: 1px solid #eee;
  }
  input[type="checkbox"] {
    display: none;
  }
  .fas {
    font-size: 24px;
  }
  .link-button{
    text-transform: uppercase;
    font-size: 20px;
  }
  @media (min-width: 768px) {
    nav {
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
