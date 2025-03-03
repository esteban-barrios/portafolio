<script lang="ts">
  const projects: readonly {
    name: string;
    category: string;
    imgSrc: string;
    status: "Completed" | "In Develop";
  }[] = [
    {
      name: "Project 1",
      category: "Web Development",
      imgSrc: "img1.svg",
      status: "Completed",
    },
    {
      name: "Project 2",
      category: "Web Development",
      imgSrc: "img2.svg",
      status: "Completed",
    },
    {
      name: "Project 3",
      category: "Mobile Development",
      imgSrc: "img3.svg",
      status: "In Develop",
    },
    {
      name: "My Portfolio",
      category: "Web Development",
      imgSrc: "img4.svg",
      status: "In Develop",
    },
  ];
</script>

<section id="section-2" class="work">
  <div class="container">
    <h1 class="title">My <span>Work</span></h1>
    <div class="projects-wrapper">
      {#each projects as project}
        <div class="project-card">
          <div class="content">
            <span
              class="badge {project.status === 'Completed'
                ? 'completed'
                : 'in-develop'}">{project.status}</span
            >
            <i class="category">{project.category}</i>
            <h2>{project.name}</h2>
            <div class="arrow-icon">
              <img
                src="icons/top-right.svg"
                alt="{project.name} navigation arrow"
              />
            </div>
          </div>
          <div class="project-img">
            <img
              src="img/projects/{project.imgSrc}"
              alt="{project.name} preview"
            />
          </div>
        </div>
      {/each}
    </div>
  </div>
</section>

<style>
  .projects-wrapper {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, calc(50% - 2rem)));
    gap: 2rem;
    justify-content: center;
    margin-bottom: 2rem;
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
    justify-content: space-between;
    position: relative;
    gap: 1rem;
  }
  .category {
    color: #666;
  }
  .arrow-icon {
    width: 32px;
  }
  .project-img {
    flex: 1;
    display: flex;
    flex-direction: row;
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
  @media (min-width: 809px) {
    .project-card .content {
      align-items: self-start;
    }
  }

  @media (min-width: 1439px) {
  }
</style>
