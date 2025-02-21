<script lang="ts">
  const onClickButton = () => {
    let element = document.getElementById("section-1");
    element?.scrollIntoView();
  };
</script>

<section id="section-0" class="home">
  <div class="container">
    <div class="content">
      <div class="title">
        <span>Full-Stack</span>
        Developer
      </div>
      <div class="description">
        <p>
          Software Engineer graduated from Universidad Técnica Federico Santa
          María. My interest lies in web and mobile development to drive digital
          transformation in companies across the industries.<br /><br />
          I firmly believe in the premise that
          <strong
            >"A good plan today is better than a perfect plan tomorrow."</strong
          >
        </p>
      </div>
      <button onclick={onClickButton}> About Me </button>
    </div>
    <div class="img-container">
      <img src="home-img-2.png" alt="Esteban's avatar" />
    </div>
  </div>
</section>

<style>
  .home {
    background-color: #f9f9f9;
  }

  .home .content {
    display: flex;
    flex-direction: column;
    justify-content: center;
  }

  .home .img-container {
    max-width: 50vh;
    width: 80%;
    margin-inline: auto;
  }
  .home button {
    margin-top: max(2rem, 3vh);
    align-self: flex-end;
  }
  @media (min-width: 1025px) {
    .home .container {
      flex-direction: row;
      align-items: center;
    }
    .home .content {
      width: 50%;
    }
    .home .img-container {
      width: 50%;
    }
  }
</style>
