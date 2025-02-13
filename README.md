<body>
    


    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>تایمر عشق ❤️</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #ffe6e6;
            color: #d63384;
            padding: 20px;
        }
        h1 {
            font-size: 24px;
        }
        #timer {
            font-size: 20px;
            font-weight: bold;
            margin-top: 20px;
        }
    </style>


    <h1>⏳ از زمان اولین ولنتاینمون چقدر گذشته ❤️</h1>
    <h2>💑 Haniyeh and Hamed 💑</h2>
    <div id="timer">🗓 0 سال، 0 روز، 4 ساعت، 22 دقیقه، 57 ثانیه</div>

    <script>
        function updateTimer() {
            // تاریخ شروع (تاریخ امشب)
            let startDate = new Date("2025-02-13T00:00:00"); // اینو می‌تونی تغییر بدی
            let now = new Date();
            let diff = now - startDate; // اختلاف زمانی به میلی‌ثانیه

            // محاسبه سال، ماه، روز، ساعت، دقیقه و ثانیه
            let seconds = Math.floor(diff / 1000);
            let minutes = Math.floor(seconds / 60);
            let hours = Math.floor(minutes / 60);
            let days = Math.floor(hours / 24);
            let years = Math.floor(days / 365);
            
            days = days % 365; // محاسبه تعداد روزهای باقیمانده بعد از سال کامل
            hours = hours % 24;
            minutes = minutes % 60;
            seconds = seconds % 60;

            document.getElementById("timer").innerHTML = 
                `🗓 ${years} سال، ${days} روز، ${hours} ساعت، ${minutes} دقیقه، ${seconds} ثانیه`;
        }

        setInterval(updateTimer, 1000); // به‌روزرسانی هر ثانیه
        updateTimer(); // اولین اجرا بلافاصله بعد از لود شدن صفحه
    </script>


  

    <script type="text/javascript">

  </script>

  <script>
    // tell the embed parent frame the height of the content
    if (window.parent && window.parent.parent){
      window.parent.parent.postMessage(["resultsFrame", {
        height: document.body.getBoundingClientRect().height,
        slug: ""
      }], "*")
    }

    // always overwrite window.name, in case users try to set it manually
    window.name = "result"
  </script>

  <script>
    const allLines = []
    const cssElement = document.querySelector("#compiled-css")

    window.addEventListener("message", (message) => {
        if (message.data.console){
          let insert = document.querySelector("#insert")
          allLines.push(message.data.console.payload)
          insert.innerHTML = allLines.join(";\r")

          let result = eval.call(null, message.data.console.payload)
          if (result !== undefined){
            console.log(result)
          }
        }

      if (message.data.css){
        cssElement.textContent = message.data.css.payload
      }

      if (message.data.html){
        document.body.innerHTML = message.data.html.payload
      }
    })
  </script>
</body>
