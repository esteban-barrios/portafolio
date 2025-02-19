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
        <h1>Software</h1>
        Engineer
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
      <button onclick={onClickButton}> Read More </button>
    </div>
    <div class="img-container">
      <img src="home-img-2.png" alt="Esteban's avatar" />
    </div>
  </div>
</section>

<style>
  .home {
    background-color: whitesmoke;
  }
  .home .container {
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
  }
  .home .content {
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
  .home .title h1 {
    font-size: inherit;
    background: linear-gradient(to right, #b86adf, #ff6c63, #ffb147);
    background-clip: text;
    color: transparent;
    margin-right: 0.5rem;
  }
  .home .title {
    margin-bottom: min(2rem, 3vh);
    font-size: clamp(1.75rem, 3vw + 1rem, 4rem);
    text-transform: uppercase;
  }
  .home .description p {
    margin-bottom: max(2rem, 3vh);
    font-size: clamp(0.85rem, 1vw + 0.5rem, 1rem);
    line-height: 1.6;
    max-width: 100%;
    word-wrap: break-word;
  }
  .home .img-container {
    max-width: 20rem;
    width: 80%;
    margin-inline: auto;
  }
  .home button {
    align-self: flex-end;
  }
  @media (min-width: 1024px) {
    .home .container {
      flex-direction: row;
      align-items: center;
    }
    .home .content {
      width: 50%;
    }
    .home .img-container {
      max-width: 40rem;
      width: 50%;
    }
  }
</style>
