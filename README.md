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
    const today =
