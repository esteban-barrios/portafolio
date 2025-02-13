<script lang="ts">
  import LinkButton from "$lib/components/LinkButton.svelte";
</script>

<nav class="side-bar">
  <h1>Esteban</h1>
  <button>hamburger</button>
  <ul>
    <LinkButton text = {"home"}/>
    <LinkButton text = {"experience"}/>
    <LinkButton text = {"skills"}/>
    <LinkButton text = {"projects"}/>
    <LinkButton text = {"contact"}/>
  </ul>
</nav>

<style>
  h1 {
    color: white;
    font-weight: 400;
  }
  ul {
    margin-top: clamp(4rem, 50%, 8rem);
  }
  button{
    display: none;
  }
  .side-bar {
      position: fixed;
      left: 0;
      top: 0;
      width: clamp(6.25rem, 14%, 16.25rem);
      height: 100dvh;
      padding: 2rem;
      background-color: #141313;
      transition: all 0.3s ease-in-out;
  }

  @media (max-width: 540px) {
      .side-bar {
          width: 100%;  
          width: -webkit-fill-available;  
          height: 4rem;
          top: 0;
          left: 0;
          display: flex;
          align-items: center;
          justify-content: space-between;
          padding: 0 1rem;
      }
      ul {
        display: none;
      }
      button {
        display: block;
        width: 100px;
      }
  }
</style>