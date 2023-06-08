- 👋 Hi, I’m @docGenius3
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
docGenius3/docGenius3 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
<!-- HTML File created by Jose Rodriguez -->

<!DOCTYPE html>
<html>
<head>
    <style>
        /* Styling to center the buttons and the image */
        .center {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }

        /* Styling to make the buttons look nice */
        button {
            margin: 10px;
            padding: 10px;
            font-size: 20px;
        }

        /* Styling to make the meme image visible and movable */
        #meme-img {
            position: absolute;
            top: 50%;
            left: 50%;
        }
    </style>
</head>
<body>
    <div class="center">
        <!-- Start Button -->
        <button id="start-button" onclick="startMoving()">Start</button>
        <!-- Stop Button -->
        <button id="stop-button" onclick="stopMoving()" disabled>Stop</button>
    </div>

    <!-- Meme image -->
    <img id="meme-img" src="meme.jpg">

    <script src="script.js"></script>
</body>
</html>// JavaScript File

// Variable to hold the setInterval ID
let intervalId;

// Function to start moving the meme image
function startMoving() {
    // Disabling the start button
    document.getElementById("start-button").disabled = true;
    // Enabling the stop button
    document.getElementById("stop-button").disabled = false;

    // Get the meme image
    const memeImg = document.getElementById("meme-img");

    // Start the meme image moving side to side
    let direction = 1;
    intervalId = setInterval(function() {
        const left = memeImg.style.left.replace('px', '');
        if (left > window.innerWidth - memeImg.width || left < 0) {
            direction *= -1;  // Reverse direction when hitting an edge
        }
        memeImg.style.left = (parseInt(left) + 10 * direction) + 'px';
    }, 100);
}

// Function to stop moving the meme image
function stopMoving() {
    // Disabling the stop button
    document.getElementById("stop-button").disabled = true;
    // Enabling the start button
    document.getElementById("start-button").disabled = false;

    // Stop the meme image from moving
    clearInterval(intervalId);
}






