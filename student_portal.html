<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Student Exam Portal</title>
    <style>
        body { font-family: Arial; background-color: #f0f0f0; padding: 30px; }
        .container { background: #fff; padding: 20px; border-radius: 10px; max-width: 600px; margin: auto; box-shadow: 0 0 10px rgba(0,0,0,0.1); }
        input, button { width: 100%; padding: 10px; margin: 10px 0; font-size: 16px; }
        .option { padding: 10px; margin-bottom: 10px; border: 1px solid #ccc; border-radius: 5px; cursor: pointer; background-color: #f9f9f9; }
        .option:hover { background-color: #eaeaea; }
        .hidden { display: none; }
        #timer { font-weight: bold; color: #d9534f; margin-top: 10px; }
    </style>
</head>
<body>
    <div class="container" id="register">
        <h2>Student Registration</h2>
        <input type="text" id="name" placeholder="Enter your name">
        <input type="text" id="roll" placeholder="Enter your Roll Number">
        <input type="text" id="phone" placeholder="Enter your Phone Number">
        <button onclick="startExam()">Start Exam</button>
    </div>

    <div class="container hidden" id="quiz">
        <h3 id="question">Question appears here</h3>
        <div id="options"></div>
        <div id="timer">Time Left: <span id="time">30</span>s</div>
    </div>

    <div class="container hidden" id="thankyou">
        <h2>Thank you for completing the exam!</h2>
    </div>

    <script>
        const quizData = [
            { question: "What is the capital of France?", options: ["Berlin", "Madrid", "Paris", "Lisbon"], answer: "Paris" },
            { question: "Which language is used for web development?", options: ["Python", "HTML", "Java", "C++"], answer: "HTML" },
            { question: "Who wrote 'Hamlet'?", options: ["Charles Dickens", "Shakespeare", "Mark Twain", "Jane Austen"], answer: "Shakespeare" }
        ];

        let currentQuestion = 0, score = 0, timer, timeLeft = 30;
        let name, roll, phone;

        function startExam() {
            name = document.getElementById("name").value.trim();
            roll = document.getElementById("roll").value.trim();
            phone = document.getElementById("phone").value.trim();

            if (!name || !roll || !phone) {
                alert("Fill all fields!");
                return;
            }

            const data = JSON.parse(localStorage.getItem("studentData")) || [];
            const disqualified = JSON.parse(localStorage.getItem("disqualifiedRolls")) || [];

            if (data.find(e => e.roll === roll) || disqualified.includes(roll)) {
                alert("Roll number already used or disqualified!");
                return;
            }

            document.getElementById("register").classList.add("hidden");
            document.getElementById("quiz").classList.remove("hidden");

            loadQuestion();
            startTimer();
            monitorTabSwitch(); // Monitor tab/window switch
        }

        function loadQuestion() {
            if (currentQuestion >= quizData.length) {
                endExam();
                return;
            }

            document.getElementById("question").innerText = quizData[currentQuestion].question;
            const optionsBox = document.getElementById("options");
            optionsBox.innerHTML = "";

            quizData[currentQuestion].options.forEach(opt => {
                const btn = document.createElement("div");
                btn.className = "option";
                btn.innerText = opt;
                btn.onclick = () => {
                    if (opt === quizData[currentQuestion].answer) score++;
                    currentQuestion++;
                    loadQuestion();
                };
                optionsBox.appendChild(btn);
            });
        }

        function startTimer() {
            timeLeft = 30;
            document.getElementById("time").innerText = timeLeft;
            timer = setInterval(() => {
                timeLeft--;
                document.getElementById("time").innerText = timeLeft;
                if (timeLeft <= 0) {
                    clearInterval(timer);
                    endExam();
                }
            }, 1000);
        }

        function endExam() {
            clearInterval(timer);
            document.getElementById("quiz").classList.add("hidden");
            document.getElementById("thankyou").classList.remove("hidden");

            const data = JSON.parse(localStorage.getItem("studentData")) || [];
            data.push({ name, roll, phone, score, date: new Date().toLocaleString() });
            localStorage.setItem("studentData", JSON.stringify(data));
        }

        function disqualifyStudent(reason) {
            clearInterval(timer);
            alert("You switched tabs or minimized the window. You are disqualified!\nReason: " + reason);

            // Save disqualified roll
            const disqualified = JSON.parse(localStorage.getItem("disqualifiedRolls")) || [];
            if (!disqualified.includes(roll)) {
                disqualified.push(roll);
                localStorage.setItem("disqualifiedRolls", JSON.stringify(disqualified));
            }

            // End exam forcibly
            document.getElementById("quiz").classList.add("hidden");
            document.getElementById("thankyou").classList.remove("hidden");
        }

        function monitorTabSwitch() {
            document.addEventListener("visibilitychange", () => {
                if (document.hidden) {
                    disqualifyStudent("Tab/window switch detected.");
                }
            });

            window.addEventListener("blur", () => {
                disqualifyStudent("Window lost focus.");
            });
        }
    </script>
</body>
</html>
