<script lang="ts">
  import "$lib/global.css";
  import SideBar from "$lib/components/SideBar.svelte";

  let { children } = $props();
</script>


<SideBar/>
<main>
  {@render children()}
</main>

<style>
 main {
    position: fixed;
    left: clamp(6.25rem + 4rem, 14% + 4rem, 16.25rem + 4rem);
    width: 100%;  
    width: -webkit-fill-available;
    height: 100dvh;
    padding: 2rem;
    transition: all 0.3s ease-in-out;
  }

  /* Ajustes para mobile */
  @media (max-width: 540px) {
    main {
      left: 0;
      top: 4rem; /* Para quedar debajo de la barra de navegación */
      width: 100%;  
      width: -webkit-fill-available;
      height: calc(100dvh - 4rem); /* Resta la altura de la barra */
      padding: 1rem;
    }
  }
</style>
