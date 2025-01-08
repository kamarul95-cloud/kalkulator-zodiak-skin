<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kalkulator Zodiac Skin</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            font-family: Arial, sans-serif;
            background-image: url('https://i.ibb.co/FkvQppP/IMG-20250108-WA0089.jpg');
            background-size: 150%;
            background-position: center;
            background-attachment: fixed;
            color: white;
            text-shadow: 1px 1px 2px black;
        }

        .calculator {
            background-color: rgba(0, 0, 0, 0.7);
            padding: 20px;
            border-radius: 10px;
            max-width: 400px;
            margin: 50px auto;
            text-align: center;
        }

        .calculator input,
        .calculator select {
            margin: 10px 0;
            padding: 10px;
            font-size: 1rem;
            border-radius: 5px;
            border: none;
            width: 100%;
        }

        .calculator button {
            margin: 10px 0;
            padding: 10px;
            font-size: 1.1rem;
            font-weight: bold;
            border-radius: 5px;
            border: none;
            width: 100%;
            background-color: #ff9800;
            color: white;
            cursor: pointer;
            transition: background-color 0.3s ease, transform 0.2s ease;
        }

        .calculator button:hover {
            background-color: #e65100;
            transform: scale(1.05);
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.3);
        }

        .result {
            margin-top: 20px;
            font-weight: bold;
            font-size: 1.2rem;
        }
    </style>
</head>
<body>
    <div class="calculator">
        <h1>Kalkulator Zodiac Skin</h1>
        <label for="skins">Berapa Skin Zodiac Yang Telah Anda Miliki:</label>
        <select id="skins">
            <option value="0">0</option>
            <option value="1">1</option>
            <option value="2">2</option>
            <option value="3">3</option>
            <option value="4">4</option>
            <option value="5">5</option>
            <option value="6">6+</option>
        </select>
        <button onclick="calculate()">Kira</button>
        <div class="result" id="result"></div>
    </div>

    <script>
        function calculate() {
            const skins = parseInt(document.getElementById("skins").value);
            let points = skins * 10;
            if (skins >= 6) points = 60;

            const requiredPoints = 100 - points;
            const draws3 = Math.ceil(requiredPoints / 3);
            const coa3 = draws3 * 14;

            const draws15 = Math.ceil(requiredPoints / 1.5);
            const coa15 = draws15 * 14;

            document.getElementById("result").innerHTML = `
                <p>Poin Terkumpul: ${points}</p>
                <p>Poin Diperlukan: ${requiredPoints}</p>
                <p>Jika Purata Poin (3): ${draws3} cabutan, ${coa3} COA</p>
                <p>Jika Purata Poin (1.5): ${draws15} cabutan, ${coa15} COA</p>
            `;
        }
    </script>
</body>
</html>
