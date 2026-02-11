<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Will You Be My Valentine?</title>
    
    <link href="https://fonts.googleapis.com/css2?family=Fredoka+One&family=Quicksand:wght@400;700&display=swap" rel="stylesheet">

    <style>
        /* --- GENERAL STYLES --- */
        body {
            background-color: #ffc0cb; /* Cute Pink */
            font-family: 'Quicksand', sans-serif;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            margin: 0;
            text-align: center;
            overflow-x: hidden;
        }

        h1 {
            font-family: 'Fredoka One', cursive;
            color: #d32f2f;
            font-size: 3rem;
            margin-bottom: 20px;
            padding: 0 10px;
        }

        .gif-container img {
            max-width: 90%;
            height: auto;
            border-radius: 15px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
        }

        /* --- BUTTONS (Step 1) --- */
        .buttons {
            margin-top: 30px;
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            align-items: center;
            gap: 20px;
        }

        .btn {
            padding: 15px 30px;
            font-size: 1.2rem;
            border: none;
            border-radius: 50px; /* Pill Shape */
            cursor: pointer;
            transition: all 0.3s ease;
            font-family: 'Fredoka One', cursive;
            box-shadow: 0 4px 6px rgba(0,0,0,0.2);
        }

        #yes-btn {
            background-color: #4CAF50; /* Green */
            color: white;
        }

        #no-btn {
            background-color: #f44336; /* Red */
            color: white;
        }

        /* --- DASHBOARD GRID (Step 2) --- */
        .hidden {
            display: none !important;
        }

        #grid-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
            margin-top: 30px;
            background: rgba(255, 255, 255, 0.5);
            padding: 20px;
            border-radius: 20px;
        }

        .grid-item {
            width: 150px;
            height: 150px;
            background-color: white;
            border-radius: 15px; /* Square with rounded corners */
            border: none;
            cursor: pointer;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            box-shadow: 0 4px 10px rgba(0,0,0,0.1);
            transition: transform 0.2s;
        }

        .grid-item:hover {
            transform: scale(1.05);
        }

        .grid-item img {
            width: 80px;
            height: 80px;
            object-fit: contain;
        }

        /* --- SUB PAGES --- */
        .sub-page {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: #ffe4e1;
            z-index: 100;
            overflow-y: auto;
            display: flex;
            flex-direction: column;
            align-items: center;
            padding-top: 50px;
        }

        .back-btn {
            margin-bottom: 20px;
            padding: 10px 20px;
            background-color: #555;
            color: white;
            border: none;
            border-radius: 20px;
            cursor: pointer;
        }

        .content-box {
            background: white;
            padding: 30px;
            border-radius: 15px;
            max-width: 80%;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
        }

        /* Specific Styles for Content */
        #gallery {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 10px;
        }
        
        #gallery img {
            width: 150px;
            height: 150px;
            object-fit: cover;
            border-radius: 10px;
        }
    </style>
</head>
<body>

    <div id="asking-container">
        <div class="gif-container">
            <img id="main-gif" src="ask.gif" alt="Cute begging gif" onerror="this.src='https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExcDdtZ2JiZDR0a3lvMWF4OG8yc3p6Ymdvd3g2dXh4Z3p4aXdyeW9nim&ep=v1_stickers_search&rid=giphy.gif&ct=s'"> 
            </div>

        <h1 id="main-text">Will you be my Valentine?</h1>

        <div class="buttons">
            <button id="yes-btn" class="btn">Yes</button>
            <button id="no-btn" class="btn">No</button>
        </div>
    </div>

    <div id="dashboard-container" class="hidden">
        <div class="gif-container">
            <img id="success-gif" src="happy.gif" alt="Happy gif" onerror="this.src='https://media.giphy.com/media/T86i6yDyOYz7J6dPhf/giphy.gif'">
        </div>
        
        <h1>YAY! I knew you'd say yes! ❤️</h1>
        <p>Choose a surprise:</p>

        <div id="grid-container">
            <button class="grid-item" onclick="showPage('page-letter')">
                <img src="letter.png" alt="Letter" onerror="this.src='https://cdn-icons-png.flaticon.com/512/3062/3062634.png'">
                <span>Letter</span>
            </button>

            <button class="grid-item" onclick="showPage('page-flower')">
                <img src="flower.png" alt="Flower" onerror="this.src='https://cdn-icons-png.flaticon.com/512/1892/1892751.png'">
                <span>Flowers</span>
            </button>

            <button class="grid-item" onclick="showPage('page-gift')">
                <img src="gift.png" alt="Gift" onerror="this.src='https://cdn-icons-png.flaticon.com/512/4213/4213958.png'">
                <span>Present</span>
            </button>

            <button class="grid-item" onclick="showPage('page-photos')">
                <img src="couple.png" alt="Us" onerror="this.src='https://cdn-icons-png.flaticon.com/512/4804/4804246.png'">
                <span>Us</span>
            </button>
        </div>
    </div>

    <div id="page-letter" class="sub-page hidden">
        <button class="back-btn" onclick="hidePage('page-letter')">⬅ Back</button>
        <div class="content-box">
            <h2>My Love Letter to You</h2>
            <p>
                Dear [Her Name],<br><br>
                I am so happy you are my Valentine. You mean the world to me...
                <br><br>
                (Edit this text in the HTML file!)
            </p>
        </div>
    </div>

    <div id="page-flower" class="sub-page hidden">
        <button class="back-btn" onclick="hidePage('page-flower')">⬅ Back</button>
        <h2>For You! 🌹</h2>
        <img src="bouquet.png" style="width: 300px;" onerror="this.src='https://media.giphy.com/media/26BRv0ThflsHCqDrG/giphy.gif'">
    </div>

    <div id="page-gift" class="sub-page hidden">
        <button class="back-btn" onclick="hidePage('page-gift')">⬅ Back</button>
        <div class="content-box">
            <h2>Your Gift!</h2>
            <p>You get a <strong>Plushy of your choice</strong> AND a <strong>Blind Box!</strong></p>
            <img src="plushy_box.png" style="width: 200px;" onerror="this.src='https://cdn-icons-png.flaticon.com/512/4531/4531388.png'">
        </div>
    </div>

    <div id="page-photos" class="sub-page hidden">
        <button class="back-btn" onclick="hidePage('page-photos')">⬅ Back</button>
        <h2>Our Cute Moments</h2>
        <div id="gallery">
            <img src="photo1.jpg" alt="Us 1" onerror="this.style.display='none'">
            <img src="photo2.jpg" alt="Us 2" onerror="this.style.display='none'">
            <img src="photo3.jpg" alt="Us 3" onerror="this.style.display='none'">
            </div>
        <p style="margin-top: 20px;">(Add your real photos to the folder!)</p>
    </div>

    <script>
        const yesBtn = document.getElementById("yes-btn");
        const noBtn = document.getElementById("no-btn");
        const mainText = document.getElementById("main-text");
        
        const askingContainer = document.getElementById("asking-container");
        const dashboardContainer = document.getElementById("dashboard-container");

        let noClickCount = 0;
        const noPhrases = [
            "No", 
            "Are you sure?", 
            "Really sure?", 
            "Pookie please...", 
            "Don't do this to me!", 
            "I'm gonna cry...", 
            "You're breaking my heart ;(", 
            "I'm gonna die...", 
            "Plsssss", 
            "Pretty please?",
            "You don't have a choice lol"
        ];

        // LOGIC: When 'No' is clicked
        noBtn.addEventListener("click", function() {
            noClickCount++;
            
            // 1. Change Text (cycle through array)
            const phraseIndex = Math.min(noClickCount, noPhrases.length - 1);
            mainText.innerText = noPhrases[phraseIndex];

            // 2. Make Yes Button Bigger
            const currentFontSize = parseFloat(window.getComputedStyle(yesBtn).fontSize);
            const newFontSize = currentFontSize * 1.5;
            yesBtn.style.fontSize = newFontSize + "px";
            
            // 3. Make No Button Smaller (until it disappears)
            const currentPadding = parseFloat(window.getComputedStyle(noBtn).padding);
            const newPadding = Math.max(0, currentPadding - 5); // reduce padding
            
            if (newPadding <= 5) {
                noBtn.style.display = 'none'; // hide it eventually
            } else {
                noBtn.style.padding = newPadding + "px";
            }
        });

        // LOGIC: When 'Yes' is clicked
        yesBtn.addEventListener("click", function() {
            // Hide Asking Screen
            askingContainer.classList.add("hidden");
            
            // Show Dashboard
            dashboardContainer.classList.remove("hidden");
        });

        // NAVIGATION FUNCTIONS
        function showPage(pageId) {
            document.getElementById(pageId).classList.remove("hidden");
        }

        function hidePage(pageId) {
            document.getElementById(pageId).classList.add("hidden");
        }
    </script>
</body>
</html>
