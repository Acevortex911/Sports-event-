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
    h1, h2 {
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
    .event-card h3 {
      margin-top: 0;
    }
    #eventSection {
      display: none;
    }
    @media (max-width: 600px) {
      body {
        padding: 1rem;
      }
      input, button {
        font-size: 0.9rem;
      }
    }
  </style>
</head>
<body>

  <h1>Find Players for Your Sport</h1>

  <div id="signInSection">
    <h2>Sign In</h2>
    <form id="signInForm">
      <input type="email" id="email" placeholder="Email" required />
      <input type="tel" id="phone" placeholder="Phone Number" required />
      <button type="submit">Sign In</button>
    </form>
  </div>

  <div id="eventSection">
    <h2>Post an Event</h2>
    <form id="eventForm">
      <input type="text" id="sport" placeholder="Sport (e.g. Soccer, Basketball)" required />
      <input type="text" id="location" placeholder="Location" required />
      <label for="date"><strong>Date of the Event:</strong></label>
      <input type="date" id="date" required />
      <input type="time" id="time" required />
      <button type="submit">Post Event</button>
    </form>

    <h2>Event Stream</h2>
    <div id="eventsContainer"></div>
  </div>

  <script>
    const signInForm = document.getElementById('signInForm');
    const eventForm = document.getElementById('eventForm');
    const signInSection = document.getElementById('signInSection');
    const eventSection = document.getElementById('eventSection');
    const eventsContainer = document.getElementById('eventsContainer');

    let signedInUser = {};

    // Restrict past dates in date picker
    const dateInput = document.getElementById('date');
    const today = new Date().toISOString().split("T")[0];
    dateInput.setAttribute('min', today);

    signInForm.addEventListener('submit', function (e) {
      e.preventDefault();

      const email = document.getElementById('email').value;
      const phone = document.getElementById('phone').value;

      if (email && phone) {
        signedInUser = { email, phone };
        signInSection.style.display = 'none';
        eventSection.style.display = 'block';
      }
    });

    eventForm.addEventListener('submit', function (e) {
      e.preventDefault();

      const sport = document.getElementById('sport').value;
      const location = document.getElementById('location').value;
      const date = document.getElementById('date').value;
      const time = document.getElementById('time').value;

      const selectedDate = new Date(date);
      const now = new Date();
      now.setHours(0,0,0,0);

      if (selectedDate < now) {
        alert('Please select a date that is today or in the future.');
        return;
      }

      if (sport && location && date && time && signedInUser.email && signedInUser.phone) {
        const card = document.createElement('div');
        card.className = 'event-card';
        card.innerHTML = `
          <h3>${sport}</h3>
          <p><strong>Location:</strong> ${location}</p>
          <p><strong>Date:</strong> ${date}</p>
          <p><strong>Time:</strong> ${time}</p>
          <p><strong>Posted by:</strong> ${signedInUser.email} (${signedInUser.phone})</p>
        `;
        eventsContainer.appendChild(card);
        eventForm.reset();
      } else {
        alert('Please fill out all fields.');
      }
    });
  </script>
</body>
</html>
