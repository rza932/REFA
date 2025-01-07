<!DOCTYPE html>
<html lang="fa">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>وب‌سایت من</title>
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
        }
        header {
            background-color: #007bff;
            color: white;
            padding: 1rem;
        }
        nav a {
            color: white;
            text-decoration: none;
            margin: 0 10px;
        }
        nav a:hover {
            text-decoration: underline;
        }
        section {
            padding: 2rem;
        }
        footer {
            background-color: #007bff;
            color: white;
            padding: 1rem;
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
    <!-- وارد کردن Web3Modal و Web3.js -->
    <script src="https://cdn.jsdelivr.net/npm/web3modal@1.9.0/dist/index.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/web3@1.6.1/dist/web3.min.js"></script>
</head>
<body>
    <header>
        <h1>به وب‌سایت من خوش آمدید</h1>
        <nav>
            <a href="#about">درباره</a>
            <a href="#services">خدمات</a>
            <a href="#contact">تماس</a>
        </nav>
    </header>
    <section id="about">
        <h2>درباره من</h2>
        <p>این اولین وب‌سایت من است که با کمک HTML ساخته شده است.</p>
    </section>
    <section id="services">
        <h2>خدمات</h2>
        <p>ما بهترین خدمات را ارائه می‌دهیم.</p>
    </section>
    <section id="contact">
        <h2>تماس</h2>
        <p>ایمیل: example@example.com</p>
    </section>
    
    <!-- دکمه اتصال به ولت -->
    <div>
        <button class="connect-wallet-btn" onclick="connectWallet()">Connect Wallet</button>
    </div>

    <footer>
        <p>&copy; 2025 تمام حقوق محفوظ است.</p>
    </footer>

    <script>
        // تنظیم Web3Modal
        let web3Modal;
        let provider;

        async function connectWallet() {
            try {
                // بررسی اینکه MetaMask یا کیف پول مشابه در دسترس است
                if (typeof window.ethereum !== 'undefined') {
                    // درخواست اتصال به حساب‌ها
                    const accounts = await window.ethereum.request({ method: 'eth_requestAccounts' });
                    alert('Wallet connected: ' + accounts[0]);
                } else {
                    alert('MetaMask not detected. Please install MetaMask.');
                }
            } catch (error) {
                // مدیریت خطاها
                if (error.code === 4001) {
                    alert('User rejected the connection request');
                } else {
                    alert('Error connecting wallet: ' + error.message);
                }
            }
        }
    </script>
</body>
</html>

                alert('MetaMask not detected. Please install MetaMask.');
            }
        }
    </script>
</body>
</html>
