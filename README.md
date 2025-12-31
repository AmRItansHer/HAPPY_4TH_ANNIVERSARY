<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Birthday Surprise for My Love</title>
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@400;700&display=swap" rel="stylesheet"> <!-- For fancy font -->
    <style>
        body { margin: 0; padding: 0; font-family: 'Arial', sans-serif; overflow: hidden; }
        .page { position: absolute; top: 0; left: 0; width: 100%; height: 100vh; display: none; justify-content: center; align-items: center; flex-direction: column; text-align: center; }
        .page.active { display: flex; }
        
        /* Page 1: Galaxy BG with Red Square and Small Hearts Background */
        #page1 { background: linear-gradient(to bottom, #000428, #004e92); position: relative; overflow: hidden; }
        #page1::before { content: ''; position: absolute; top: 0; left: 0; width: 100%; height: 100%; background-image: radial-gradient(circle, ❤️ 1px, transparent 1px); background-size: 20px 20px; opacity: 0.3; pointer-events: none; }
        .red-square { border: 3px solid red; padding: 30px; background: rgba(255, 255, 255, 0.9); border-radius: 10px; box-shadow: 0 0 10px rgba(0,0,0,0.5); max-width: 400px; position: relative; z-index: 1; }
        .red-square p { font-size: 18px; color: #333; margin: 10px 0; }
        .heart { font-size: 60px; color: red; cursor: pointer; margin: 10px 0; }
        .progress-bar { width: 250px; height: 25px; background: #ddd; margin-top: 15px; border-radius: 12px; overflow: hidden; }
        .progress-fill { height: 100%; background: linear-gradient(to right, red, darkred); width: 0%; }
        
        /* Page 2: Big Heart BG */
        #page2 { background: linear-gradient(to bottom, #ffcccc, #ffe6e6); }
        .heart-tap { font-size: 120px; cursor: pointer; margin-bottom: 10px; }
        .knock-message { font-size: 16px; color: black; margin-bottom: 20px; font-weight: bold; }
        .letter { display: none; background: white; padding: 25px; margin-top: 20px; border-radius: 15px; max-width: 700px; text-align: left; box-shadow: 0 0 15px rgba(0,0,0,0.3); font-family: 'Dancing Script', cursive; font-size: 18px; line-height: 1.6; color: #333; font-weight: bold; }
        .letter p { margin: 10px 0; }
        .next-btn { display: none; margin-top: 25px; padding: 12px 25px; background: red; color: white; border: none; cursor: pointer; border-radius: 8px; font-size: 16px; font-weight: bold; }
        
        /* Page 3: Birthday Doodles - Dark Red BG, Pink Text */
        #page3 { background: linear-gradient(to bottom, #8b0000, #b22222); color: #ff69b4; }
        .message { font-size: 50px; font-weight: bold; margin-bottom: 20px; text-shadow: 2px 2px 4px rgba(0,0,0,0.5); }
        .tap-btn { position: absolute; bottom: 60px; right: 20px; padding: 12px 25px; background: red; color: white; border: none; cursor: pointer; border-radius: 8px; font-size: 16px; font-weight: bold; }
        .note { position: absolute; bottom: 20px; right: 20px; font-size: 12px; color: #ff69b4; font-weight: bold; }
        
        /* Page 4: Final Wish - BG Full of Small Hearts */
        #page4 { background: linear-gradient(to bottom, #fce4ec, #f8bbd9); position: relative; overflow: hidden; }
        #page4::before { content: ''; position: absolute; top: 0; left: 0; width: 100%; height: 100%; background-image: radial-gradient(circle, ❤️ 1px, transparent 1px); background-size: 20px 20px; opacity: 0.3; pointer-events: none; }
        .top-message { font-family: 'Comic Sans MS', cursive; font-size: 40px; color: red; text-align: center; margin-bottom: 20px; text-shadow: 2px 2px 4px rgba(0,0,0,0.5); position: relative; z-index: 1; }
        .final-letter { background: #f5f5dc; padding: 25px; margin-top: 20px; border-radius: 15px; max-width: 700px; text-align: left; box-shadow: 0 0 15px rgba(0,0,0,0.3); font-size: 16px; line-height: 1.6; color: #333; position: relative; z-index: 1; }
        .final-letter p { margin: 10px 0; }
        .ending { color: #c71585; font-weight: bold; margin-top: 15px; font-size: 18px; }
        
        /* Firecracker Burst Animation - Made Bigger and More Visible */
        .cracker { position: absolute; width: 20px; height: 20px; background: radial-gradient(circle, yellow, orange, red); border-radius: 50%; pointer-events: none; animation: burst 3s ease-out forwards; z-index: 10; }
        @keyframes burst {
            0% { transform: scale(0) rotate(0deg); opacity: 1; }
            50% { transform: scale(1.5) rotate(180deg); opacity: 0.8; }
            100% { transform: scale(2) rotate(360deg) translateX(var(--tx)) translateY(var(--ty)); opacity: 0; }
        }
    </style>
</head>
<body>
    <!-- Page 1: Galaxy BG with Red Square -->
    <div id="page1" class="page active">
        <div class="red-square">
            <p>made with love open wisely</p>
            <div class="heart" id="hold-heart">❤️</div>
            <p>hold my heart for some sec</p>
            <div class="progress-bar">
                <div class="progress-fill" id="progress-fill"></div>
            </div>
        </div>
    </div>
    
    <!-- Page 2: Big Heart BG -->
    <div id="page2" class="page">
        <div class="heart-tap" id="tap-heart">🫀</div>
        <div class="knock-message">KNOCK KNOCK MY HEART TWO TIME YOU FIND SOMETHING FROM MY HEART</div>
        <div class="letter" id="letter">
            <p>Hello my love;</p>
            <p>I know ki itte saal nah tha mei tumhare saath aurr pata nahi mujhe tumne kaise banay apne pichle 19 birthday but yee aapka 20th birthday the journey of your 20's start here and mei isko aapka best birthday banaunga and from know to till your 80's aapka har birthday best birthday hoga.</p>
        </div>
        <button class="next-btn" id="next-btn">Next</button>
    </div>
    
    <!-- Page 3: Birthday Doodles -->
    <div id="page3" class="page">
        <div class="message">FEW MORE MOMENTS</div>
        <button class="tap-btn" id="tap-btn">FINAL BIRTHDAY WISH</button>
        <div class="note">NOTE: OPEN ONLY IF CLOCK SAYS 23:59:58</div>
    </div>
    
    <!-- Page 4: Final Wish -->
    <div id="page4" class="page">
        <div class="top-message">HAPPIEST BIRTHDAY TO MY PRECIOUS GIRL.</div>
        <div class="final-letter">
            <p>HAPPY BIRTHDAY TO MY KUCHU PUCHU MOTUU BABU, I AM ALWAYS WITH YOU BACCHA MAY MAHADEV BLESS YOU AND GIVE WHATEVER YOU WANT MERE HISSE KI KISMAT AAPKO DEDE MERE HISSE KA PYAAR AAPKO DEDE AAPKO HUMESHA KHUSH RAKHE AAPKE FAMILY KE PAS RAKHE AND BAS JAISE KRIPA BARSA RAHE PLEASE WAISE BARSATE RAHE.</p>
            <div class="ending">I LOVE YOU BACCHA>>>>3</div>
        </div>
    </div>
    
    <script>
        // Page 1: Hold heart to fill progress bar progressively (5 seconds)
        let holdStart = null;
        let animationId = null;
        const progressFill = document.getElementById('progress-fill');
        
        function updateProgress() {
            if (holdStart) {
                const elapsed = Date.now() - holdStart;
                const progress = Math.min((elapsed / 5000) * 100, 100);
                progressFill.style.width = progress + '%';
                if (progress < 100) {
                    animationId = requestAnimationFrame(updateProgress);
                }
            }
        }
        
        document.getElementById('hold-heart').addEventListener('mousedown', () => {
            holdStart = Date.now();
            progressFill.style.width = '0%';
            updateProgress();
        });
        
        document.getElementById('hold-heart').addEventListener('touchstart', (e) => {
            e.preventDefault();
            holdStart = Date.now();
            progressFill.style.width = '0%';
            updateProgress();
        });
        
        document.getElementById('hold-heart').addEventListener('mouseup', () => {
            if (animationId) cancelAnimationFrame(animationId);
            if (holdStart && (Date.now() - holdStart) >= 5000) {
                document.getElementById('page1').classList.remove('active');
                document.getElementById('page2').classList.add('active');
            }
            holdStart = null;
        });
        
        document.getElementById('hold-heart').addEventListener('touchend', () => {
            if (animationId) cancelAnimationFrame(animationId);
            if (holdStart && (Date.now() - holdStart) >= 5000) {
                document.getElementById('page1').classList.remove('active');
                document.getElementById('page2').classList.add('active');
            }
            holdStart = null;
        });
        
        // Page 2: Tap heart twice to reveal letter, then show button after 15 sec
        let tapCount = 0;
        document.getElementById('tap-heart').addEventListener('click', () => {
            tapCount++;
            if (tapCount === 2) {
                document.getElementById('letter').style.display = 'block';
                setTimeout(() => {
                    document.getElementById('next-btn').style.display = 'block';
                }, 15000);
            }
        });
        document.getElementById('next-btn').addEventListener('click', () => {
            document.getElementById('page2').classList.remove('active');
            document.getElementById('page3').classList.add('active');
        });
        
        // Page 3: Tap button to go to final page
        document.getElementById('tap-btn').addEventListener('click', () => {
            document.getElementById('page3').classList.remove('active');
            document.getElementById('page4').classList.add('active');
            setTimeout(burstCrackers, 500); // Delay burst slightly for page load
        });
        
        // Firecracker Burst Function for Page 4 - Enhanced for Visibility
        function burstCrackers() {
            const page4 = document.getElementById('page4');
            const numCrackers = 100; // More particles for better effect
            for (let i = 0; i < numCrackers; i++) {
                const cracker = document.createElement('div');
                cracker.className = 'cracker';
                cracker.style.left = Math.random() * 100 + '%';
                cracker.style.top = Math.random() * 100 + '%';
                cracker.style.setProperty('--tx', (Math.random() - 0.5) * 200 + 'px'); // Random direction
                cracker.style.setProperty('--ty', (Math.random() - 0.5) * 200 + 'px');
                cracker.style.animationDelay = Math.random() * 1 + 's'; // Stagger
                page4.appendChild(cracker);
                
                // Remove cracker after animation
                setTimeout(() => {
                    if (cracker.parentNode) cracker.remove();
                }, 3000);
            }
        }
    </script>
</body>
</html>


A PROMPT USED:
no like start a website with a galaxy image in bg and a red hallow sqare in which written made with love 
open wisely and heart below this line and below hearrt written hold my heart for some sec and heart is 
surorrounded with a bar which increses when we hold the heart and as bar fully increse in around 5 sec main 
website open so first page is like in bg one big real human heart and on tapping that heart 2 time heart will 
open in two part from between  and the heart now become letter and the letter is like " Hello my love;
I know ki itte saal nah tha mei tumhare saath aurr pata nahi mujhe tumne kaise banay apne pichle 19 birthday but 
yee aapka 20th birthday the journey of your 20's start here and mei isko aapka best birthday banaunga and from 
know to till your 80's aapka har birthday best birthday hoga." below this letter a button appear after 10-20 
second after opening of that heart and on tapping on this button user move toward to next page where a full
birthday doodles apeard ballons fire cracker are bursting and A bold messege on center of the page " FEW MORE MOMENTS"
in red colour and in bottom right corner written " FINAL BIRTHDAY WISH " in 8pt. sizr and a note below 
" NOTE: TAP ONLY IF THE CLOCK SAYS 23:59:58." and on tapping that button a last grand birthday wish page appear
in which on top a messege witten in hear font and hesrt colour " HAPPIEST BIRTHDAY TO MY PRECIOUS GIRL." below 
that a letter whose bg is of creame colour in which " HAPPY BIRTHDAY TO MY KUCHU PUCHU MOTUU BABU, I AM ALWAYS 
WITH YOU BACCHA MAY MAHADEV BLESS YOU AND GIVE WHATEVER YOU WANT MERE HISSE KI KISMAT AAPKO DEDE MERE HISSE KA 
PYAAR AAPKO DEDE AAPKO HUMESHA KHUSH RAKHE AAPKE FAMILY KE PAS RAKHE AND BAS JAISE KRIPA BARSA RAHE PLEASE WAISE 
BARSATE RAHE." and in end with dark pink colour written " I LOVE YOU BACCHA>>>>3" and this page bg is in light medium
pink and in bg fire crackers are bursting.
