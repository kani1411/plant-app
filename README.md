<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Plant Tracker App</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }

        header {
            text-align: center;
            padding: 20px;
            background-color: #4CAF50;
            color: white;
            font-size: 24px;
        }

        section {
            margin: 20px 0;
        }

        form {
            display: flex;
            flex-direction: column;
            max-width: 300px;
            margin: 0 auto;
        }

        label {
            margin-bottom: 8px;
        }

        input, button {
            margin-bottom: 16px;
            padding: 8px;
        }

        button {
            background-color: #4CAF50;
            color: white;
            border: none;
            cursor: pointer;
        }

        button:hover {
            background-color: #45a049;
        }

        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
        }

        th, td {
            border: 1px solid #ddd;
            padding: 8px;
            text-align: left;
        }

        th {
            background-color: #4CAF50;
            color: white;
        }
    </style>
</head>
<body>

    <header>
        <h1>Plant Tracker App</h1>
    </header>

    <section>
        <h2>Add a New Plant</h2>
        <form id="plantForm">
            <label for="plantName">Plant Name:</label>
            <input type="text" id="plantName" name="plantName" required>

            <label for="wateringFrequency">Watering Frequency (days):</label>
            <input type="number" id="wateringFrequency" name="wateringFrequency" required>

            <button type="button" onclick="addPlant()">Add Plant</button>
        </form>
    </section>

    <section>
        <h2>Plants to Track</h2>
        <table id="plantTable">
            <thead>
                <tr>
                    <th>Plant Name</th>
                    <th>Watering Frequency (days)</th>
                </tr>
            </thead>
            <tbody>
                <!-- Plant entries will be added here dynamically -->
            </tbody>
        </table>
    </section>

    <script>
        function addPlant() {
            // Get values from the form
            var plantName = document.getElementById("plantName").value;
            var wateringFrequency = document.getElementById("wateringFrequency").value;

            // Add a new row to the table
            var table = document.getElementById("plantTable").getElementsByTagName('tbody')[0];
            var newRow = table.insertRow(table.rows.length);
            var cell1 = newRow.insertCell(0);
            var cell2 = newRow.insertCell(1);
            cell1.innerHTML = plantName;
            cell2.innerHTML = wateringFrequency;

            // Clear the form
            document.getElementById("plantForm").reset();
        }
    </script>

</body>
</html>
