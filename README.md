# event-count-down-timer<!DOCTYPE html>
<html>
<head>
  <title>Event Countdown Timer</title>
  <style>
    body {
      text-align: center;
      font-family: Arial, sans-serif;
      font-size: 24px;
    }

    #countdown {
      font-weight: bold;
    }
  </style>
</head>
<body>
  <h1>Event Countdown Timer</h1>
  <div id="countdown"></div>

  <script>
    // Set the date and time of the event
    var eventDate = new Date("June 30, 2023 00:00:00").getTime();

    // Update the countdown every second
    var countdown = setInterval(function() {
      // Get the current date and time
      var now = new Date().getTime();

      // Calculate the remaining time
      var remainingTime = eventDate - now;

      // Calculate days, hours, minutes, and seconds
      var days = Math.floor(remainingTime / (1000 * 60 * 60 * 24));
      var hours = Math.floor((remainingTime % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
      var minutes = Math.floor((remainingTime % (1000 * 60 * 60)) / (1000 * 60));
      var seconds = Math.floor((remainingTime % (1000 * 60)) / 1000);

      // Display the countdown
      document.getElementById("countdown").innerHTML = days + "d " + hours + "h " + minutes + "m " + seconds + "s ";

      // If the countdown is over, display a message
      if (remainingTime < 0) {
        clearInterval(countdown);
        document.getElementById("countdown").innerHTML = "The event has already occurred.";
      }
    }, 1000);
  </script>
</body>
</html>
