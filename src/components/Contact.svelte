<section id="contact">
    <h2>Contact Me</h2>
    <form>
      <label for="name">Name:</label>
      <input type="text" id="name" placeholder="Your Name" required />
  
      <label for="email">Email:</label>
      <input type="email" id="email" placeholder="Your Email" required />
  
      <label for="message">Message:</label>
      <textarea id="message" placeholder="Your Message" required></textarea>
  
      <button type="submit">Send</button>
    </form>
  </section>
  
  <style>
    form {
      display: flex;
      flex-direction: column;
      gap: 1rem;
      max-width: 400px;
      margin: 0 auto;
    }
    input, textarea {
      padding: 0.5rem;
      border: 1px solid #ccc;
      border-radius: 4px;
    }
    button {
      padding: 0.5rem;
      background: #007BFF;
      color: white;
      border: none;
      border-radius: 4px;
      cursor: pointer;
    }
  </style>