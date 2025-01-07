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
        .wallet-options {
            display: flex;
            justify-content: center;
            margin-top: 30px;
        }
        .wallet-option {
            margin: 0 10px;
            cursor: pointer;
        }
        .wallet-option img {
            width: 50px;
            height: 50px;
            border-radius: 10px;
            transition: transform 0.3s;
        }
        .wallet-option img:hover {
            transform: scale(1.1);
        }
    </style>
</head>
<body>
    <header>
        <h1>انتخاب کیف پول</h1>
    </header>

    <div>
        <p>لطفا کیف پول مورد نظر خود را انتخاب کنید:</p>

        <div class="wallet-options">
            <!-- آیکون‌های کیف پول -->
            <div class="wallet-option" onclick="connectWithMetaMask()">
                <img src="https://cryptologos.cc/logos/metamask-mask-logo.png" alt="MetaMask">
            </div>
            <div class="wallet-option" onclick="connectWithWalletConnect()">
                <img src="https://cryptologos.cc/logos/walletconnect-wallet-logo.png" alt="WalletConnect">
            </div>
            <!-- اینجا می‌توانید آیکون کیف پول‌های دیگر مانند Proton و Tonkeeper را اضافه کنید -->
        </div>

    </div>

    <footer>
        <p>&copy; 2025 تمام حقوق محفوظ است.</p>
    </footer>

    <script>
        // متدهای اتصال به کیف پول

        // اتصال به MetaMask
        async function connectWithMetaMask() {
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

        // اتصال به WalletConnect (این می‌تواند برای کیف پول‌های دیگر نیز باشد)
        async function connectWithWalletConnect() {
            const provider = new WalletConnectProvider({
                infuraId: "INFURA_PROJECT_ID" // اضافه کردن شناسه Infura خود
            });

            try {
                await provider.enable();
                const web3 = new Web3(provider);
                const accounts = await web3.eth.getAccounts();
                alert('Wallet connected: ' + accounts[0]);
            } catch (error) {
                alert('Error connecting WalletConnect: ' + error.message);
            }
        }
    </script>

    <!-- وارد کردن WalletConnectProvider -->
    <script src="https://cdn.jsdelivr.net/npm/@walletconnect/web3-provider/dist/umd/index.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/web3/dist/web3.min.js"></script>
</body>
</html>
