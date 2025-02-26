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
    margin-bottom: 2rem;
  }

  .form-col {
    display: flex;
    flex-direction: column;
    justify-content: center;
  }

  .form-col:first-child {
    display: none;
  }

  .form-col form {
    display: flex;
    flex-direction: column;
    justify-content: start;
    padding: 2rem;
  }

  form label {
    display: flex;
    flex-direction: column;
    font-weight: bold;
    width: 100%;
    text-transform: uppercase;
    color: white;
  }

  .form-col form input,
  .form-col form textarea {
    margin-bottom: 1rem;
    padding: 0.5rem;
    border: none;
    border-radius: 10px;
    background: rgba(20, 20, 19, 0.1);
    color: white;
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
    .form-col form {
      padding: 0;
    }
    .form-container {
      display: grid;
      grid-template-columns: 50% 40%;
      gap:2rem;
      align-items: center;
      justify-content: center;
      padding: 2rem;
    }
    .image-container img {
      object-fit: cover;
      border-radius: 5px;
    }
  }
</style>
