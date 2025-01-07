<!DOCTYPE html>
<html lang="fa">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>اتصال به کیف پول</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #f4f4f9;
            color: #333;
            margin: 0;
            padding: 0;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
        }
        header {
            background-color: #007bff;
            color: white;
            padding: 1rem;
            width: 100%;
        }
        footer {
            background-color: #007bff;
            color: white;
            padding: 1rem;
            position: fixed;
            width: 100%;
            bottom: 0;
        }
        .connect-wallet-btn {
            background-color: #28a745;
            color: white;
            padding: 10px 20px;
            font-size: 16px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            margin-top: 20px;
        }
        .connect-wallet-btn:hover {
            background-color: #218838;
        }
    </style>
</head>
<body>
    <header>
        <h1>اتصال به MetaMask</h1>
    </header>

    <div>
        <p>برای اتصال به کیف پول MetaMask خود، روی دکمه زیر کلیک کنید:</p>
        <button class="connect-wallet-btn" onclick="connectMetaMask()">Connect MetaMask</button>
    </div>

    <footer>
        <p>&copy; 2025 تمام حقوق محفوظ است.</p>
    </footer>

    <script>
        async function connectMetaMask() {
            if (typeof window.ethereum !== 'undefined') {
                try {
                    const accounts = await window.ethereum.request({ method: 'eth_requestAccounts' });
                    alert('Wallet connected: ' + accounts[0]);
                } catch (error) {
                    alert('Error connecting MetaMask: ' + error.message);
                }
            } else {
                alert('MetaMask not detected. Please install MetaMask.');
            }
        }
    </script>
</body>
</html>
