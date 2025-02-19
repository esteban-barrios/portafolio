<section id="section-1" class="about">
  <div class="container">
    <div class="content">
      <h1 class="title">about <span>me</span></h1>
      <p>
        Experienced software developer with expertise in HTML, JavaScript,
        TypeScript, CSS, SQL, Python, C, C#, Java, Dart, Ruby, and PHP. <br /><br />
        Proficient in developing and maintaining applications across various frameworks
        and environments, including Angular, React, Flutter, Node.js, Django, Ruby
        on Rails, and WordPress. Skilled in database management with PostgreSQL and MongoDB, as well as deployment
        and cloud services using Docker, AWS EC2, Docker Hub, and GitHub. Capable
        of creating scalable, high-performance solutions with efficient CI/CD pipelines.
      </p>
    </div>
    <!-- Timeline Section -->
    <div class="timeline">
      <div class="timeline-col">
        <div class="company">
          <h3>Social Web, Chile</h3>
          <p>January 2021 - July 2020</p>
        </div>
        <div class="company">
          <h3>IBM, Chile</h3>
          <p>March 2023 - August 2023</p>
        </div>
      </div>
      <div class="timeline-col">
        <div class="circle orange"></div>
        <div class="line"></div>
        <div class="circle dark"></div>
      </div>
      <div class="timeline-col">
        <div class="role">
          <h3>Frontend Developer</h3>
          <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
        </div>
        <div class="role">
          <h3>Intern</h3>
          <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
        </div>
      </div>
    </div>
    <button> Resume </button>
  </div>
</section>

<style>
  .about {
    background: white;
  }

  .about .container {
    height: 100%;
    display: flex;
    flex-direction: column;
    gap:2rem;
  }

  /* Timeline Styling */
  .timeline {
    display: flex;
    flex-wrap: wrap;
  }

  .timeline-col {
    display: flex;
    justify-content: space-between;
    flex-direction: column;
    width: 33%;
    gap: 2rem;
  }

  .timeline-col:nth-child(2) {
    align-items: center;
    position: relative;
  }

  .company,
  .role {
    padding: 10px;
  }

  .company h3,
  .role h3 {
    margin: 0;
    font-size: 1.2em;
  }

  .company p,
  .role p {
    margin: 5px 0;
    color: #666;
  }

  /* Círculos */
  .circle {
    width: 40px;
    height: 40px;
    border-radius: 50%;
    border: 2px dashed #000; /* Borde punteado */
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: white;
    position: relative;
    z-index: 1;
  }

  .circle::before {
    content: "";
    width: 24px;
    height: 24px;
    border-radius: 50%;
    background-color: #ff6b00; /* Color del círculo interno */
  }

  .circle.dark::before {
    background-color: #1a1f2b; /* Color diferente para el segundo círculo */
  }

  /* Línea punteada entre los círculos */
  .line {
    position: absolute;
    width: 2px;
    height: calc(100% - 40px); /* Ajusta la línea para que conecte los círculos */
    background: repeating-linear-gradient(
      to bottom,
      #000,
      #000 5px,
      transparent 5px,
      transparent 10px
    ); /* Línea punteada */
    top: 30px;
    left: 50%;
    transform: translateX(-50%);
    z-index: 0;
  }

  .about button{
    align-self: center;
  }

  /* Responsive */
  @media (max-width: 768px) {
    .timeline {
      display: flex;
      flex-direction: column;
      align-items: center;
    }

    .timeline-col {
      width: 100%;
      align-items: center;
    }

    .line {
      height: 50px;
    }
  }
</style>
