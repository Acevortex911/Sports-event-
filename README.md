<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sports Buddy - Find & Join Local Sports!</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
      tailwind.config = {
        theme: {
          extend: {
            fontFamily: {
              // Use Inter font
              sans: ['Inter', 'sans-serif'],
            },
          }
        }
      }
    </script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style type="text/tailwindcss">
        /* Custom base styles if needed */
        body {
            @apply antialiased; /* Smoother font rendering */
        }
    </style>
</head>
<body class="bg-gradient-to-b from-gray-50 to-gray-100 font-sans text-gray-800">

    <header class="relative text-white text-center mb-10 shadow-lg bg-cover bg-center py-12 md:py-16 lg:py-20"
            style="background-image: url('https://placehold.co/1920x400/cccccc/666666?text=Sports+Banner+Placeholder');">
            {/* IMPORTANT: Replace the placeholder URL above with your actual banner image URL! */}

            {/* Semi-transparent overlay - Adjusted for better contrast */}
            <div class="absolute inset-0 bg-blue-800/75"></div> {/* Simplified overlay, increased opacity */}

            {/* Container for text content, positioned above overlay */}
            <div class="container relative z-10 max-w-5xl mx-auto px-4 sm:px-6 lg:px-8">
                 {/* Ensured white text and stronger shadow for readability */}
                <h1 class="text-4xl md:text-5xl lg:text-6xl font-bold mb-3 text-white drop-shadow-lg">Sports Buddy</h1>
                <p class="text-lg md:text-xl text-gray-100 drop-shadow-md">Your community for finding and joining local sports activities!</p>
            </div>
    </header>

    <main class="container max-w-5xl mx-auto px-4 sm:px-6 lg:px-8">

        <section id="search-filter" class="bg-white p-6 rounded-xl shadow-lg mb-10 border border-gray-200">
            <h2 class="text-2xl font-semibold text-center mb-6 text-gray-700">Find Activities Near Oakville</h2>
            <form class="flex flex-wrap gap-4 items-end">
                <div class="form-group flex flex-col flex-1 min-w-[180px]">
                    <label for="sport" class="mb-2 font-semibold text-gray-600 text-sm">Sport:</label>
                    <select id="sport" name="sport" class="p-3 border border-gray-300 rounded-lg shadow-sm focus:ring-2 focus:ring-blue-500 focus:border-transparent transition duration-150 ease-in-out text-sm">
                        <option value="">-- Select Sport --</option>
                        <option value="basketball">Basketball</option>
                        <option value="soccer">Soccer</option>
                        <option value="tennis">Tennis</option>
                        <option value="volleyball">Volleyball</option>
                        <option value="running">Running</option>
                        <option value="cycling">Cycling</option>
                        <option value="yoga">Yoga</option>
                        <option value="hiking">Hiking</option>
                        <option value="pickleball">Pickleball</option>
                        <option value="badminton">Badminton</option>
                        <option value="other">Other</option>
                    </select>
                </div>
                <div class="form-group flex flex-col flex-1 min-w-[200px]">
                    <label for="location" class="mb-2 font-semibold text-gray-600 text-sm">Location:</label>
                    <input type="text" id="location" name="location" placeholder="Oakville, ON or Postal Code" class="p-3 border border-gray-300 rounded-lg shadow-sm focus:ring-2 focus:ring-blue-500 focus:border-transparent transition duration-150 ease-in-out text-sm">
                </div>
                 <div class="form-group flex flex-col flex-1 min-w-[150px]">
                    <label for="distance" class="mb-2 font-semibold text-gray-600 text-sm">Distance (km):</label>
                    <select id="distance" name="distance" class="p-3 border border-gray-300 rounded-lg shadow-sm focus:ring-2 focus:ring-blue-500 focus:border-transparent transition duration-150 ease-in-out text-sm">
                        <option value="5">5 km</option>
                        <option value="10" selected>10 km</option>
                        <option value="25">25 km</option>
                        <option value="50">50 km</option>
                    </select>
                </div>
                <button type="button" class="p-3 bg-green-500 text-white rounded-lg shadow-md hover:bg-green-600 focus:outline-none focus:ring-2 focus:ring-green-500 focus:ring-offset-2 transition duration-150 ease-in-out font-medium h-[50px] transform hover:scale-105">Search</button>
            </form>
        </section>

        <section id="activity-list">
            <h2 class="text-3xl font-semibold mb-8 text-gray-800 border-b border-gray-300 pb-3">Upcoming Activities</h2>

            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">

                <div class="activity-card bg-white border border-gray-200 rounded-xl p-6 shadow-md hover:shadow-xl transition duration-300 ease-in-out transform hover:-translate-y-1 flex flex-col justify-between">
                    <div>
                        <h3 class="text-xl font-bold mb-3 text-blue-700">Basketball Pickup Game</h3>
                        <p class="sport-type italic text-gray-500 text-xs mb-3">Sport: Basketball 🏀</p>
                        <p class="location mb-2 text-gray-600 text-sm">📍 Location: Queen Elizabeth Park CC, Oakville</p>
                        <p class="time mb-2 text-gray-600 text-sm">⏰ Time: Today, 6:00 PM</p>
                        <p class="participants mb-1 text-gray-600 text-sm">👥 Players: 8 / 10</p>
                        <p class="text-sm text-indigo-600 mt-1 font-medium">Currently 8 people participating.</p>
                    </div>
                    <button class="join-button w-full mt-4 px-5 py-2 bg-orange-500 text-white rounded-lg shadow-md hover:bg-orange-600 focus:outline-none focus:ring-2 focus:ring-orange-500 focus:ring-offset-2 transition duration-150 ease-in-out text-sm font-medium transform hover:scale-105">View & Join</button>
                </div>

                <div class="activity-card bg-white border border-gray-200 rounded-xl p-6 shadow-md hover:shadow-xl transition duration-300 ease-in-out transform hover:-translate-y-1 flex flex-col justify-between">
                    <div>
                        <h3 class="text-xl font-bold mb-3 text-blue-700">Evening Soccer Match</h3>
                        <p class="sport-type italic text-gray-500 text-xs mb-3">Sport: Soccer ⚽</p>
                        <p class="location mb-2 text-gray-600 text-sm">📍 Location: Bronte Athletic Field, Oakville</p>
                        <p class="time mb-2 text-gray-600 text-sm">⏰ Time: Tomorrow, 7:30 PM</p>
                        <p class="participants mb-1 text-gray-600 text-sm">👥 Players: 15 / 22</p>
                        <p class="text-sm text-indigo-600 mt-1 font-medium">Currently 15 people participating.</p>
                    </div>
                    <button class="join-button w-full mt-4 px-5 py-2 bg-orange-500 text-white rounded-lg shadow-md hover:bg-orange-600 focus:outline-none focus:ring-2 focus:ring-orange-500 focus:ring-offset-2 transition duration-150 ease-in-out text-sm font-medium transform hover:scale-105">View & Join</button>
                </div>

                 <div class="activity-card bg-white border border-gray-200 rounded-xl p-6 shadow-md hover:shadow-xl transition duration-300 ease-in-out transform hover:-translate-y-1 flex flex-col justify-between">
                    <div>
                        <h3 class="text-xl font-bold mb-3 text-blue-700">Lakeside Yoga Session</h3>
                        <p class="sport-type italic text-gray-500 text-xs mb-3">Sport: Yoga 🧘‍♀️</p>
                        <p class="location mb-2 text-gray-600 text-sm">📍 Location: Coronation Park, Oakville</p>
                        <p class="time mb-2 text-gray-600 text-sm">⏰ Time: Sunday, 9:00 AM</p>
                        <p class="participants mb-1 text-gray-600 text-sm">👥 Spots: 12 / 20</p>
                        <p class="text-sm text-indigo-600 mt-1 font-medium">Currently 12 people participating.</p>
                    </div>
                    <button class="join-button w-full mt-4 px-5 py-2 bg-orange-500 text-white rounded-lg shadow-md hover:bg-orange-600 focus:outline-none focus:ring-2 focus:ring-orange-500 focus:ring-offset-2 transition duration-150 ease-in-out text-sm font-medium transform hover:scale-105">View & Join</button>
                </div>

                 <div class="activity-card bg-white border border-gray-200 rounded-xl p-6 shadow-md hover:shadow-xl transition duration-300 ease-in-out transform hover:-translate-y-1 flex flex-col justify-between">
                    <div>
                        <h3 class="text-xl font-bold mb-3 text-blue-700">Bronte Creek Trail Hike</h3>
                        <p class="sport-type italic text-gray-500 text-xs mb-3">Sport: Hiking 🌲</p>
                        <p class="location mb-2 text-gray-600 text-sm">📍 Location: Bronte Creek Provincial Park</p>
                        <p class="time mb-2 text-gray-600 text-sm">⏰ Time: Saturday, 10:00 AM</p>
                        <p class="participants mb-1 text-gray-600 text-sm">👥 Group Size: 6 / 15</p>
                        <p class="text-sm text-indigo-600 mt-1 font-medium">Currently 6 people participating.</p>
                    </div>
                    <button class="join-button w-full mt-4 px-5 py-2 bg-orange-500 text-white rounded-lg shadow-md hover:bg-orange-600 focus:outline-none focus:ring-2 focus:ring-orange-500 focus:ring-offset-2 transition duration-150 ease-in-out text-sm font-medium transform hover:scale-105">View & Join</button>
                </div>

                 <div class="activity-card bg-white border border-gray-200 rounded-xl p-6 shadow-md hover:shadow-xl transition duration-300 ease-in-out transform hover:-translate-y-1 flex flex-col justify-between">
                    <div>
                        <h3 class="text-xl font-bold mb-3 text-blue-700">Casual Pickleball Play</h3>
                        <p class="sport-type italic text-gray-500 text-xs mb-3">Sport: Pickleball 🥒</p>
                        <p class="location mb-2 text-gray-600 text-sm">📍 Location: Glen Abbey CC, Oakville</p>
                        <p class="time mb-2 text-gray-600 text-sm">⏰ Time: Monday, 11:00 AM</p>
                        <p class="participants mb-1 text-gray-600 text-sm">👥 Players: 4 / 4</p>
                        <p class="text-sm text-indigo-600 mt-1 font-medium">Currently 4 people participating.</p>
                    </div>
                    <button class="join-button w-full mt-4 px-5 py-2 bg-red-500 text-white rounded-lg shadow-md focus:outline-none focus:ring-2 focus:ring-red-500 focus:ring-offset-2 transition duration-150 ease-in-out text-sm font-medium cursor-not-allowed">Full</button>
                </div>

                 <div class="activity-card bg-white border border-gray-200 rounded-xl p-6 shadow-md hover:shadow-xl transition duration-300 ease-in-out transform hover:-translate-y-1 flex flex-col justify-between">
                    <div>
                        <h3 class="text-xl font-bold mb-3 text-blue-700">Waterfront Cycling Group</h3>
                        <p class="sport-type italic text-gray-500 text-xs mb-3">Sport: Cycling 🚴‍♂️</p>
                        <p class="location mb-2 text-gray-600 text-sm">📍 Location: Start at Tannery Park, Oakville</p>
                        <p class="time mb-2 text-gray-600 text-sm">⏰ Time: Sunday, 8:00 AM</p>
                        <p class="participants mb-1 text-gray-600 text-sm">👥 Riders: 5 / ∞ (Open group)</p>
                        <p class="text-sm text-indigo-600 mt-1 font-medium">Currently 5 people participating.</p>
                    </div>
                    <button class="join-button w-full mt-4 px-5 py-2 bg-orange-500 text-white rounded-lg shadow-md hover:bg-orange-600 focus:outline-none focus:ring-2 focus:ring-orange-500 focus:ring-offset-2 transition duration-150 ease-in-out text-sm font-medium transform hover:scale-105">View & Join</button>
                </div>

            </div>
             </section>

        <section id="about-section" class="bg-gradient-to-r from-teal-50 to-blue-50 p-8 rounded-xl shadow-lg my-12 border border-gray-200">
            <h2 class="text-3xl font-semibold text-center mb-6 text-gray-800">About Sports Buddy</h2>
            <p class="text-center text-gray-700 max-w-3xl mx-auto leading-relaxed">
                Sports Buddy was created to make finding and participating in local sports easier than ever! Whether you're looking for a competitive match, a casual game, or just a group to exercise with, our goal is to connect you with fellow sports enthusiasts in the Oakville community and beyond.
            </p>
            <p class="text-center text-gray-700 max-w-3xl mx-auto leading-relaxed mt-4">
                We believe playing sports together builds community, promotes health, and is just plain fun. So go ahead, find your next game and make some new buddies!
            </p>
            <div class="mt-8 text-center">
                 <a href="#" class="text-blue-600 hover:text-blue-800 font-medium transition duration-150 ease-in-out">Learn More About Us &rarr;</a>
            </div>
        </section>

    </main>

    <footer class="bg-gradient-to-r from-cyan-700 to-blue-800 text-gray-100 text-center py-12 mt-12 shadow-inner">
        <div class="container max-w-5xl mx-auto px-4 sm:px-6 lg:px-8">

            <p class="text-base mb-4">&copy; 2025 Sports Buddy. Connecting players in Oakville & beyond.</p>

            <div class="mt-4 text-sm space-x-4 md:space-x-6">
                <a href="#" class="text-gray-200 hover:text-white hover:underline mx-2 transition duration-150">Privacy Policy</a> |
                <a href="#" class="text-gray-200 hover:text-white hover:underline mx-2 transition duration-150">Terms of Service</a> |
                <a href="#" class="text-gray-200 hover:text-white hover:underline mx-2 transition duration-150">Contact Us</a>
            </div>

            <div class="mt-6 text-sm">
                <a href="https://docs.google.com/presentation/d/1YYxvSlJy0tOw7woy4fpTJ4g3RgybRVye6xkjD-F-SbU/edit?usp=sharing"
                   target="_blank" rel="noopener noreferrer"
                   class="text-gray-200 hover:text-white mx-2 underline transition duration-150">
                   View Project Slideshow
                </a>
            </div>
        </div>
    </footer>

</body>
</html>
