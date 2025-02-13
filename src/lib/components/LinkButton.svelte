<script lang="ts">
  let {text} = $props();
</script>

<li class="link-button">
  <a href="/"> {text} </a>
</li>

<style>
  .link-button{
    margin:2rem 0rem;
    text-transform: uppercase;
    font-size: 20px;
  }
  a { 
    color:white;
  }
</style>