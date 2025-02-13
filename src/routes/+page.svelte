<script lang="ts">
  import {sections} from "./shared"
</script>

{#each sections.list as section,i}
  <section id="section-{i}" class="{section}">{section}</section>
{/each}

<style>

  section {
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 2rem;
  }
  .home { background: #f4a261; }
  .experience { background: #e76f51; }
  .skills { background: #2a9d8f; }
  .projects { background: #264653; color: white; }
  .contact { background: #8ecae6; }
</style>