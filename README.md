<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Find Sports Players</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 2rem;
      max-width: 700px;
      margin: auto;
    }
    h1 {
      text-align: center;
    }
    form {
      display: grid;
      gap: 10px;
      margin-bottom: 30px;
    }
    input, button {
      padding: 10px;
      font-size: 1rem;
    }
    .event-card {
      border: 1px solid #ccc;
      border-radius: 12px;
      padding: 1rem;
      margin-bottom: 15px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    }
    .event-card h2 {
      margin-top: 0;
    }
    /* Add some basic styling for responsiveness */
    @media (max-width: 600px) {
      body {
        padding: 1rem;
      }
      h1 {
        font-size: 1.5rem;
      }
      input, button {
        font-size: 0.9rem;
      }
    }
  </style>
</head>
<body>

  <h1>Find Players for Your Sport</h1>

  <form id="eventForm">
    <input type="text" id="sport" placeholder="Sport (e.g. Soccer, Basketball)" required />
    <input type="text" id="location" placeholder="Location" required />
    <input type="date" id="date" required />
    <input type="time" id="time" required />
    <input type="text" id="contact" placeholder="Contact Info (Email or Phone)" required />
    <button type="submit">Post Event</button>
  </form>

  <div id="eventsContainer"></div>

  <script>
    const form = document.getElementById('eventForm');
    const eventsContainer = document.getElementById('eventsContainer');

    form.addEventListener('submit', function (e) {
      e.preventDefault();

      const sport = document.getElementById('sport').value;
      const location = document.getElementById('location').value;
      const date = document.getElementById('date').value;
      const time = document.getElementById('time').value;
      const contact = document.getElementById('contact').value;

      if (sport && location && date && time && contact) {
        const card = document.createElement('div');
        card.className = 'event-card';
        card.innerHTML = `
          <h2>${sport}</h2>
          <p><strong>Location:</strong> ${location}</p>
          <p><strong>Date:</strong> ${date}</p>
          <p><strong>Time:</strong> ${time}</p>
          <p><strong>Contact:</strong> ${contact}</p>
        `;

        eventsContainer.appendChild(card);
        form.reset(); // Reset the form after posting the event
      } else {
        alert('Please fill out all fields!');
      }
    });
  </script>
</body>
</html>



