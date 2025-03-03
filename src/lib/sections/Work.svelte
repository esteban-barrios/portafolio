<script lang="ts">
  const projects: readonly {
    name: string;
    category: string;
    imgSrc: string;
    status: "Completed" | "In Develop";
  }[] = [
    { name: "Project 1", category: "Web Development", imgSrc: "img1.svg", status: "Completed" },
    { name: "Project 2", category: "Web Development", imgSrc: "img2.svg", status: "Completed" },
    { name: "Project 3", category: "Mobile Development", imgSrc: "img3.svg", status: "In Develop" },
    { name: "My Portfolio", category: "Web Development", imgSrc: "img4.svg", status: "In Develop" },
  ];
</script>

<section id="section-2" class="work">
  <div class="container">
    <h1 class="title">My <span>Work</span></h1>
    <div class="projects-wrapper">
      {#each projects as project}
        <div class="project-card">
          <span class="badge {project.status === 'Completed' ? 'completed' : 'in-develop'}">{project.status}</span>
          <div class="content">
            <i class="category">{project.category}</i>
            <h3>{project.name}</h3>
            <img
              class="arrow-icon"
              src="icons/top-right.svg"
              alt="{project.name} navigation arrow"
            />
          </div>
          <div class="project-img">
            <img src="img/projects/{project.imgSrc}" alt="{project.name} preview" />
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
  .projects-wrapper {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 2rem;
    justify-content: center;
  }
  .project-card {
    position: relative;
    flex-shrink: 0;
    display: flex;
    flex-direction: row;
    align-items: center;
    padding: 1rem;
    gap: 1rem;
    border-radius: 8px;
    cursor: pointer;
    background-color: white;
    box-shadow: 8px 8px 16px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s ease-in-out;
  }
  .project-card:hover {
    transform: scale(1.05);
  }
  .project-card .content {
    flex: 1;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 1rem;
  }
  .category {
    font-size: 0.9rem;
    color: #666;
  }
  .arrow-icon {
    width: 32px;
    margin: auto;
  }
  .project-img {
    flex: 1;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .project-img img {
    max-width: 100%;
    height: auto;
    border-radius: 5px;
    object-fit: cover;
  }
  .badge {
    position: absolute;
    top: 10px;
    left: 10px;
    padding: 5px 10px;
    font-size: 0.8rem;
    font-weight: bold;
    color: white;
    border-radius: 5px;
  }
  .completed {
    background-color: #28a745;
  }
  .in-develop {
    background-color: #fd7e14;
  }
  @media (min-width: 768px) {
    .project-card .content {
      align-items: self-start;
    }
  }
</style>
