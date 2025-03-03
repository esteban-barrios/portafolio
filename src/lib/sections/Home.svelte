<script lang="ts">
  const onClickButton = () => {
    let element = document.getElementById("section-3");
    element?.scrollIntoView();
  };
</script>

<section id="section-0" class="home">
  <div class="container">
    <div class="content">
      <h1 class="title">
        <span>Full-Stack</span>
        Developer
      </h1>
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
      <button onclick={onClickButton}> Get in Touch </button>
    </div>
    <div class="img-container">
      <img src="img/home-img.png" alt="Esteban's avatar" />
    </div>
  </div>
</section>

<style>
  .home {
    justify-content: space-around;
  }
  .home .content {
    display: flex;
    flex-direction: column;
    justify-content: center;
  }

  .home .img-container {
    max-width: 50vh;
    margin-inline: auto;
  }
  .home button {
    margin-top: max(2rem, 3vh);
  }
  @media (min-width: 1439px) {
    .home {
      justify-content: space-around;
    }
    .home .container {
      flex-direction: row;
      align-items: center;
    }
    .home .content {
      width: 50%;
      margin-inline: none;
    }
    .home .img-container {
      width: 50%;
    }
    .home button{
      align-self: flex-end;
    }
  }
</style>
