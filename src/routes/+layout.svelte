<script lang="ts">
  import "$lib/global.css";

  let { children } = $props();

  let sections = ["home", "about", "work", "contact"];
  let currentSection = $state(0);
  let isOpen = $state(false);
  let y = $state(0);
  let height = $state(0);
  let section_height = $derived(height/(sections.length));
  
  const handleOnScroll = () => {
    let percentage = y / (height-section_height) * 100;
    if (percentage >= 85 ){
      currentSection = 3;
    }
    else if (percentage >= 50 ){
      currentSection = 2;
    }
    else if (percentage >= 25 ){
      currentSection = 1;
    }
    else{
      currentSection = 0;
    }
  }
</script>

<svelte:window bind:scrollY={y} />
<svelte:document onscroll={handleOnScroll} />

<nav>
  <div class="logo">Esteban</div>
    
  <label class="hamburguer">
    <input type="checkbox" bind:checked={isOpen} />
    <i class="fas {isOpen ? 'fa-times' : 'fa-bars'}" ></i>
  </label>

  <ul class="menu {isOpen ? 'active' : ''}">
    {#each sections as section, i}
      <li class="link {currentSection === i ? 'active' : ''}">
        <a href="#section-{i}">{section}</a>
      </li>
    {/each}
  </ul>
</nav>
  
<main bind:clientHeight={height}>
  {@render children()}
</main>


<style>
  nav {
    position: fixed;
    width: 100%;
    width: -webkit-fill-available;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    font-size: 1.25rem;
    padding: 2rem;
  }
  .logo {
    font-size: 2rem;
    font-family: "Monsieur La Doulaise", serif;
    font-weight: 400;
  }
  .menu{
    display: none;
    width: 100%;
  }
  .menu.active {
    display: block;
  }
  .link {
    position: relative;
    cursor: pointer;
    transition: color 0.3s ease;
    text-transform: uppercase;
    margin-top: 1rem;
    z-index: 1;
  }
  .link.active{
    font-weight: bold;
  }

  input[type="checkbox"] {
    display: none;
  }
  .fas {
    font-size: 1.25rem;
  }

  @media (min-width: 768px) {
    nav {
      height: 100dvh;
      width: min(15%, 15rem);
      background-color: #141313;
      flex-direction: column;
      justify-content: start;
      align-items: start;
      gap:1rem;
    }
    .logo{
      margin-bottom: 2rem;
      color:white;
    }
    .link{
      color:white;
    }
    main {
      width: max(85% - 4rem, 100% - 15rem - 4rem);
      margin-left: min(15% + 4rem, 15rem + 4rem);
    }
    .hamburguer{
      display:none;
    }
    .menu {
      display: contents;
    }
    .link{
      position: relative;
      cursor: pointer;
      transition: color 0.3s ease;
      display: inline-block;
    }
    .link.active::after {
      content: "";
      position: absolute;
      left: 50%;
      bottom: 0.4rem;
      width: 100%;
      height: 0.25rem;
      transition: all 0.3s ease;
      transform: translateX(-50%); /* Centrar la línea con el texto */
      background: linear-gradient(50deg,#B86ADF, #FF6C63, #FFB147);
      z-index: -1;
    }
  }
</style>