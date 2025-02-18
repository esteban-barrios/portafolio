<script lang="ts">
  const onClickButton = () => {
    let element = document.getElementById("section-1");
    element?.scrollIntoView();
  }
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
          Software Engineer graduated from Universidad Técnica Federico Santa María. My interest lies in web and mobile development to drive digital transformation in companies across the industries.<br><br>
          I firmly believe in the premise that <strong>"A good plan today is better than a perfect plan tomorrow."</strong>
        </p>
      </div>
      <button onclick={onClickButton}> Read More </button>
    </div>
    <div class="img-container">
      <img src="home-img-2.png" alt="Esteban's avatar"/>
    </div>
  </div>
</section>

<style>

  .container {
    margin-top: 2rem;
    display: grid;
    grid-template-columns: 1fr;
    gap: 2rem;
    align-items: center;
  }
  .content {
    height: 100%;
    width: 100%;
    display: flex;
    flex-direction: column;
  }
  .title {
    font-size: clamp(1.75rem, 3vw + 1rem, 4rem);
    text-transform: uppercase;
    margin-bottom: max(10%,2rem);
  }
  .title h1 {
    font-size: inherit;
    background: linear-gradient(to right,#B86ADF, #FF6C63, #FFB147);
    background-clip: text;
    color: transparent;
    margin-right: 0.5rem;
  }
  .description p {
    font-size: clamp(.85rem, 1vw + 0.5rem, 1rem);
    line-height: 1.6; 
    max-width: 100%; 
    word-wrap: break-word;
    margin-bottom: 2rem;
  }
  .img-container {
    width: 70%;
    margin: auto;
  }
  img {
    max-width: 100%;
    height: auto;
    aspect-ratio: 1/1;
    object-fit: contain;
  }
  button {
      align-self: flex-end;
    }
  @media (min-width: 768px) {
    .container {
      width: 100%;
      margin:0;
    }   
    .img-container{
      width: 60%;
    }
  }
  @media (min-width: 1440px) {
    .container {
      grid-template-columns: 40% 60%;
    }
    .img-container{
      width: 80%;
    }
    .content {
      margin-top: 25%;
    }

    
  }
</style>
