<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kata-Kata Cinta</title>
    <style>
        body {
            margin: 0;
            padding: 20px;
            min-height: 100vh;
            font-family: 'Segoe UI', Arial, sans-serif;
            background: linear-gradient(135deg, #2c3e50, #3498db, #2980b9);
            background-size: 400% 400%;
            animation: gradientBG 8s ease infinite;
            color: #fff;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }

        .container {
            max-width: 800px;
            width: 90%;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 40px;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        @keyframes gradientBG {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        h1 {
            font-size: 2.5rem;
            margin-bottom: 30px;
            text-align: center;
            color: #ffffff;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.2);
            font-weight: 300;
            letter-spacing: 2px;
        }

        .quote-container {
            min-height: 150px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 30px 0;
        }

        .quotes {
            font-size: 1.5rem;
            line-height: 1.6;
            text-align: center;
            margin: 0;
            padding: 20px;
            border-left: 4px solid rgba(255, 255, 255, 0.3);
            transition: all 0.8s ease;
        }

        .button-container {
            text-align: center;
            margin-top: 30px;
        }

        button {
            padding: 15px 30px;
            font-size: 1.1rem;
            background: rgba(255, 255, 255, 0.2);
            border: 2px solid rgba(255, 255, 255, 0.3);
            border-radius: 50px;
            color: #fff;
            cursor: pointer;
            transition: all 0.6s ease;
            text-transform: uppercase;
            letter-spacing: 1px;
            backdrop-filter: blur(5px);
        }

        button:hover {
            background: rgba(255, 255, 255, 0.3);
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }

        @media (max-width: 650px) {
            .container {
                padding: 20px;
            }
            
            h1 {
                font-size: 2rem;
            }
            
            .quotes {
                font-size: 1.2rem;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>✨ Kata-Kata Hari Ini ✨</h1>
        <div class="quote-container">
            <p class="quotes" id="quote">Klik tombol di bawah untuk menampilkan kata-kata indah.</p>
        </div>
        <div class="button-container">
            <button onclick="generateQuote()">Tampilkan Kata-Kata</button>
        </div>
    </div>
    <footer>
        <p>&copy; MEZOYA </strong></p>
    </footer>

    <script>
        const quotes = [
            "Aku mencintaimu bukan karena siapa dirimu, tetapi karena siapa aku saat bersamamu.",
            "Cinta itu seperti angin, tak bisa dilihat, tapi bisa dirasakan.",
            "Di antara milyaran manusia di dunia ini, hatiku memilih kamu, tanpa ragu, tanpa syarat.",
            "Jika mencintaimu adalah mimpi, maka aku tidak ingin bangun selamanya.",
            "Cinta sejati bukanlah tentang memiliki, tapi tentang saling melengkapi.",
            "Aku tidak ingin menjadi segalanya bagimu, aku hanya ingin menjadi sesuatu yang berarti untukmu.",
            "Aku mencintaimu seperti bulan yang mencintai malam, selalu ada meskipun tak selalu terlihat.",
            "Dalam setiap hembusan angin, ada rindu yang kukirimkan untukmu.",
            "Mungkin aku tidak sempurna, tapi cintaku untukmu adalah hal paling sempurna yang aku punya.",
            "Jangan jadikan tatapan sebagai harapan, mungkin dia hanya melihatmu bukan menyukaimu.",
            "Mengenalnya tanpa sengaja melupakannya hampir membuatku gila, siapa sangka wajah yang semanis senja bisa membuat luka sedalam samudra.",
            "Langit itu tinggi sedangkan lautan itu dalam, jangan pernah mencintai seseorang setinggi langit jika tidak mau terluka sedalam lautan.",
            "Mencintaimu itu nyata, tapi memilikimu hanya sebatas kata, jika antartika adalah tepian bumi maka diantara kita hanya sebatas mengagumi.",
            "Tertawa namun hati terluka."
        ];

        let usedQuotes = [];
        
        function generateQuote() {
            const quoteElement = document.getElementById("quote");
            
            
            if (usedQuotes.length === quotes.length) {
                usedQuotes = [];
            }
            
            
            const availableQuotes = quotes.filter(quote => !usedQuotes.includes(quote));
            
            
            const randomIndex = Math.floor(Math.random() * availableQuotes.length);
            const selectedQuote = availableQuotes[randomIndex];
            
            
            usedQuotes.push(selectedQuote);
            
            
            quoteElement.style.opacity = 0;
            
            setTimeout(() => {
                quoteElement.textContent = selectedQuote;
                quoteElement.style.opacity = 1;
            }, 300);
        }
    </script>
</body>
</html>
