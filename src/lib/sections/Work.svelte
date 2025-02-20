<script lang="ts">
  let projects = [
    { name: "project 1", category: "Web Develop", imgSrc: "img1.svg" },
    { name: "project 2", category: "Web Develop", imgSrc: "img2.svg" },
    { name: "project 3", category: "Mobile Develop", imgSrc: "img3.svg" },
    { name: "project 4", category: "Web Develop", imgSrc: "img4.svg" },
  ];
</script>

<section id="section-2" class="work">
  <div class="container">
    <h1 class="title">My <span>work</span></h1>
    <div class="projects-container">
      {#each projects as project}
        <div class="project-card">
          <div class="content">
            <div class="project-title">
              <i>{project.category}</i>
              <h1>{project.name}</h1>
            </div>
            <img
              class="arrow-icon"
              src="top-right.svg"
              alt="{project.name}-arrow"
            />
          </div>
          <div class="project-img">
            {#if project}
              <img src={project.imgSrc} alt="{project.name}-img" />
            {/if}
          </div>
        </div>
      {/each}
    </div>
  </div>
</section>

<style>
  .work {
    background: #f9f9f9;
  }
  .projects-container {
    display: flex;
    flex-wrap: wrap;
    margin-bottom: 1rem;
    padding: 2rem 0;
    justify-content: center;
    gap:2rem;
  }

  .project-card {
    width: 100%;
    flex-shrink: 0;
    display: flex;
    flex-direction: row;
    padding:2rem;
    border-radius: 5px;
  }
  .project-card:hover {
    box-shadow: 12px 12px 12px rgba(0,0,0,0.1) , -10px -10px 10px white;
  }
  .project-card .content {
    width: 50%;
    display: flex;
    flex-direction: column;
    
  }
  .project-card h1 {
    text-transform: capitalize;
  }
  .project-img {
    width: 50%;
  }
  .project-img img {
    object-fit: cover;
  }
  .arrow-icon {
    width: 20%;
  }
  @media (min-width: 1025px) {
    .projects-container{
      justify-content: space-between;
      flex-wrap: wrap;
    }
    .project-card {
      width: 40%;
    }
  }
</style>
