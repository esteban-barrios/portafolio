<section id="section-3" class="contact">
  <div class="container">
    <h1 class="title">Got a project in <br /><span>Mind?</span></h1>
    <div class="form-container">
      <div class="form-col">
        <div class="image-container">
          <img src="contact-img.svg" alt="contact img" />
        </div>
      </div>
      <div class="form-col">
        <form method="POST">
          <label>
            Your Name
            <input type="text" name="name" placeholder="name" required />
          </label>
          <label>
            Your email
            <input type="email" name="email" placeholder="email" required />
          </label>
          <label>
            Your message
            <textarea name="message" required rows="8" placeholder="message"
            ></textarea>
          </label>
          <div class="submit-container">
            <input type="submit" value="Send Message" />
          </div>
        </form>
      </div>
    </div>
  </div>
</section>

<style>
  .contact {
    background: whitesmoke;
  }
  .form-container {
    background: linear-gradient(to right, #b86adf, #ff6c63, #ffb147);
    border-radius: 5px;
  }

  .form-col {
    min-height: 65dvh;
    width: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }

  .form-col:first-child {
    display: none;
  }

  .form-col form {
    height: 100%;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: center;
    gap: 5%;
    font-size: clamp(0.5rem, 0.5rem + 1vh, 0.85rem);
  }

  form label {
    display: flex;
    flex-direction: column;
    font-weight: bold;
    gap: 1.25rem;
    width: 40%;
    text-transform: uppercase;
    color: white;
  }

  form label:nth-child(3) {
    margin-top: 1.25rem;
    width: 85%;
  }

  .form-col form input,
  .form-col form textarea {
    width: calc(100% - 1.6rem);
    padding: 0.8rem;
    border: none;
    border-radius: 10px;
    background: rgba(20, 20, 19, 0.1);
    color: white;
    font-size: 1rem;
  }

  .form-col form input::placeholder,
  .form-col form textarea::placeholder {
    color: rgba(238, 238, 238, 0.5);
    text-transform: uppercase;
  }

  .submit-container {
    width: 85%;
    display: flex;
    justify-content: flex-end;
    padding-top: 1.25rem;
  }

  .submit-container input:last-child {
    width: max-content;
    background-color: #141313;
    color: white;
    font-weight: bold;
    text-transform: uppercase;
  }

  @media (min-width: 1025px) {
    .form-col:first-child {
      display: flex;
    }
    .form-container {
      display: grid;
      grid-template-columns: 40% 40%;
      align-items: center;
      justify-content: space-evenly;
    }
    .form-container .image-container {
      min-height: 24rem;
    }
  }
</style>
