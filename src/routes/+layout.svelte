<script lang="ts">
  import "$lib/global.css";

  let { children } = $props();

  let sections = ["home", "about", "work", "contact"];
  let currentSection = $state(0);
  let isOpen = $state(false);
  let y = $state(0);
  let height = $state(0);
  let section_height = $derived(height / sections.length);

  const handleOnScroll = () => {
    let percentage = (y / (height - section_height)) * 100;
    if (percentage >= 85) {
      currentSection = 3;
    } else if (percentage >= 50) {
      currentSection = 2;
    } else if (percentage >= 25) {
      currentSection = 1;
    } else {
      currentSection = 0;
    }
  };
  const onClickLink = (id: number) => {
    let element = document.getElementById("section-" + id);
    if (element) {
      let top = element.offsetTop + 1;
      window.scrollTo({
        top: top,
        behavior: "smooth",
      });
    }
    isOpen = !isOpen;
  };
</script>

<svelte:window bind:scrollY={y} />
<svelte:document onscroll={handleOnScroll} />

<nav>
  <div class="nav-container">
    <button class="logo" onclick={() => onClickLink(0)}>Esteban</button>
    <label class="hamburguer">
      <input id="hamburguer-toogle" type="checkbox" bind:checked={isOpen} />
      <i class="fas {isOpen ? 'fa-times' : 'fa-bars'}"></i>
    </label>
    <ul class="menu {isOpen ? 'active' : ''}">
      {#each sections as section, i}
        <li class="link {currentSection === i ? 'active' : ''}">
          <button onclick={() => onClickLink(i)}>{section}</button>
        </li>
      {/each}
    </ul>
  </div>
  <ul class="social-links">
    <li>
      <img src="linkedin-icon.svg" alt="linkedin icon" />
    </li>
    <li>
      <img src="github-icon.svg" alt="linkedin icon" />
    </li>
    <li>
      <img src="insta-icon.svg" alt="linkedin icon" />
    </li>
    <li>
      <img src="mail-icon.svg" alt="linkedin icon" />
    </li>
  </ul>
</nav>

<main bind:clientHeight={height}>
  {@render children()}
</main>

<style>
  nav {
    position: fixed;
    top: 0;
    height: 4rem;
    width: 100%;
    width: -webkit-fill-available;
    font-size: 1.25rem;
    background-color: #141313;
    color: white;
    align-content: center;
    z-index: 10;
  }
  main {
    position: absolute;
    top: 4rem;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    height: auto;
    width: 100%;
    width: -webkit-fill-available;
  }
  .nav-container {
    width: 80%;
    margin-inline: auto;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
  }
  .logo {
    font-size: 2rem;
    font-family: "Monsieur La Doulaise", serif;
    font-weight: 400;
    background-color: transparent;
    padding: 0;
    transition: all 0.3s ease;
  }
  .logo:hover{
    scale: 1.1;
  }
  .menu {
    position: fixed;
    top: 4rem;
    right: -100%;
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: start;
    transition: right 0.3s ease-in-out;
    background-color: #141313;
  }

  .menu.active {
    right: 0;
  }

  .menu li {
    position: relative;
    margin: 1rem 0;
    z-index: 0;
    transition: all 0.3s ease;
  }
  .menu li:hover {
    scale: 1.1;
  }
  .menu li.active {
    font-weight: bold;
    scale: 1.1;
  }

  .menu li.active::after {
    content: "";
    position: absolute;
    left: 50%;
    bottom: 0.4rem;
    width: 100%;
    height: 0.25rem;
    transform: translateX(-50%); /* Centrar la línea con el texto */
    background: linear-gradient(50deg, #b86adf, #ff6c63, #ffb147);
    z-index: -1;
  }

  .menu button {
    font-weight: inherit;
    background-color: transparent;
    font-size: 1.25rem;
    text-transform: uppercase;
    padding: 0 1rem 0 0;
    cursor: pointer;
  }

  input[type="checkbox"] {
    display: none;
  }
  .fas {
    font-size: 1.25rem;
  }

  .social-links {
    display: none;
  }

  @media (min-width: 768px) {
    main {
      top: 0;
      width: max(85% - 4rem, 100% - 10rem - 4rem);
      margin-left: min(15% + 4rem, 10rem + 4rem);
    }
    nav {
      height: 100dvh;
      width: min(15%, 10rem);
      padding: 0rem 2rem;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      align-items: start;
    }
    .nav-container {
      display: block;
      width: 100%;
      margin: 2rem 0rem;
    }
    .hamburguer {
      display: none;
    }
    .menu {
      position: relative;
      right: 0;
      display: block;
    }
    .link {
      display: inline-block;
    }
    .social-links {
      display: block;
    }
    .social-links li {
      display: flex;
      justify-content: center;
      align-items: center;
      width: 40px;
      height: 40px;
      border-radius: 100%;
      background-color: #383d38;
      margin-bottom: 1rem;
      cursor: pointer;
      transition: all 0.3s ease;
    }
    .social-links li:hover {
      scale: 1.1;
    }
  }
</style>
