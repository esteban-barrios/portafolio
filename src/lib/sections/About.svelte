<section id="section-1" class="about">
  <div class="container">
    <div class="content">
      <h1 class="title">about <span>me</span></h1>
      <p>
        Experienced software developer skilled in multiple languages (HTML, CSS,
        JS, TS, Python, C++, C#, PHP, Java) and frameworks (Angular, React,
        Flutter, Django, WordPress). Proficient in database management
        (PostgreSQL, MongoDB) and cloud deployment (Docker, AWS, GitHub).
        Focused on building scalable, high-performance solutions with CI/CD
        integration.
      </p>
    </div>

    <!-- Timeline Section -->
    <div class="timeline">
      <div class="timeline-item left">
        <div class="circle dark"></div>
        <div class="timeline-content">
          <h3>Social Web, Chile</h3>
          <p>January 2021 - July 2021</p>
          <h4>Frontend Developer</h4>
          <p>
            Developed UI components and improved user experience for various
            projects.
          </p>
        </div>
      </div>

      <div class="timeline-item right">
        <div class="circle orange"></div>
        <div class="timeline-content">
          <h3>IBM, Chile</h3>
          <p>March 2023 - August 2023</p>
          <h4>Intern</h4>
          <p>Assisted in cloud-based solutions and automation processes.</p>
        </div>
      </div>
    </div>

    <button>Resume <span><i class="fa-solid fa-download"></i></span> </button>
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
    justify-content: space-evenly;
  }

  .timeline {
    position: relative;
    display: flex;
    flex-direction: column;
    gap: 2rem;
    width: 100%;
  }

  .timeline-item {
    display: flex;
    align-items: center;
    gap: 1rem;
    text-align: left;
    position: relative;
    flex-direction: row;
    width: 100%;
  }

  .timeline-item.left {
    flex-direction: row;
    text-align: left;
  }

  .timeline-item.right {
    flex-direction: row-reverse;
    text-align: right;
  }
  .timeline-content {
    width: 70%;
  }

  .timeline-item .circle {
    padding: min(0.5rem, 1vh);
    border-radius: 50%;
    border: 2px dashed #141313;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: white;
    z-index: 1;
  }

  .circle::before {
    content: "";
    width: 12px;
    height: 12px;
    border-radius: 50%;
    background-color: #ff6b00;
  }

  .circle.dark::before {
    background-color: #141313;
  }

  .timeline-content h3,
  .timeline-content h4 {
    margin: 0;
    font-size: clamp(0.75rem, 1vh + 0.25rem, 0.85rem);
  }

  .timeline-content p {
    margin: 0.5rem 0;
    color: #666;
    font-size: clamp(0.5rem, 1vh + 0.25rem, 0.85rem);
  }

  .about button {
    margin-top: 1rem;
    align-self: flex-end;
    align-content: center;
  }
  .about button span {
    margin-left: 0.5rem;
  }

  @media (min-width: 768px) {
    .timeline-content {
      width: 45%;
    }
    .timeline-item.left {
      flex-direction: row-reverse;
      justify-content: flex-end;
    }
    .timeline-item.right {
      flex-direction: row;
      justify-content: flex-end;
    }
    .timeline::before {
      content: "";
      position: absolute;
      left: 50%;
      top: 25%;
      bottom: 25%;
      width: 2px;
      background: repeating-linear-gradient(
        to bottom,
        #141313,
        #141313 5px,
        transparent 5px,
        transparent 10px
      );
      transform: translateX(-50%);
      z-index: 0;
    }
    .circle {
      position: absolute;
      left: 50%;
      transform: translateX(-50%);
    }
  }
</style>
