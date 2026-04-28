
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Instant Earners</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background: #fff;
            color: #333;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 20px;
        }

        .container {
            width: 100%;
            max-width: 400px;
            background: #fff;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
            margin-top: 20px;
            position: relative;
            z-index: 1;
        }

        .header {
            background: #e60000;
            color: white;
            padding: 20px;
            text-align: center;
            font-size: 24px;
            font-weight: bold;
        }

        .form-group {
            margin-bottom: 20px;
        }

        label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: #555;
        }

        input[type="text"], input[type="password"], input[type="email"], select {
            width: 100%;
            padding: 12px;
            border: 1px solid #ddd;
            border-radius: 8px;
            font-size: 16px;
        }

        .btn {
            width: 100%;
            padding: 14px;
            border: none;
            border-radius: 8px;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
            margin-top: 10px;
        }

        .btn-red {
            background: #e60000;
            color: white;
        }

        .btn-green {
            background: #28a745;
            color: white;
        }

        .btn-back {
            background: #f0f0f0;
            color: #e60000;
            font-weight: bold;
            margin-top: 20px;
        }

        .btn-logout {
            background: #f8d7da;
            color: #721c24;
            font-weight: bold;
            margin-top: 20px;
            border: 1px solid #f5c6cb;
        }

        .links {
            display: flex;
            justify-content: space-between;
            margin-top: 20px;
            font-size: 14px;
        }

        .links a {
            color: #333;
            text-decoration: none;
            cursor: pointer;
        }

        .error {
            color: #e60000;
            font-size: 14px;
            margin-top: 10px;
            text-align: center;
            display: none;
        }

        .coming-soon {
            color: #e60000;
            font-size: 14px;
            text-align: center;
            margin-top: 10px;
            display: none;
            font-weight: bold;
        }

        .buy-login-link {
            color: #e60000;
            font-weight: bold;
            text-decoration: none;
            cursor: pointer;
            display: block;
            text-align: center;
            margin-top: 15px;
            font-size: 16px;
        }

        .spinner {
            width: 40px;
            height: 40px;
            border: 4px solid #f3f3f3;
            border-top: 4px solid #e60000;
            border-radius: 50%;
            animation: spin 1s linear infinite;
            margin: 0 auto;
        }

        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .dashboard-header {
            background: #e60000;
            color: white;
            padding: 20px;
            text-align: center;
            font-size: 22px;
            font-weight: bold;
        }

        .dashboard-red {
            background: #e60000;
            padding: 40px 20px;
            text-align: center;
            min-height: 400px;
        }

        .dash-btn {
            background: white;
            color: #e60000;
            width: 70px;
            height: 70px;
            border-radius: 12px;
            display: inline-flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            margin: 0 30px;
            font-weight: bold;
            cursor: pointer;
            -webkit-tap-highlight-color: transparent;
            touch-action: manipulation;
        }

        .dash-btn .icon {
            font-size: 28px;
            margin-bottom: 5px;
        }

        .dash-btn .label {
            font-size: 14px;
            color: #e60000;
        }

        .hidden {
            display: none !important;
        }

        .success-msg {
            text-align: center;
            padding: 40px 20px;
            font-size: 18px;
        }

        .success-msg h2 {
            color: #28a745;
            margin-bottom: 15px;
        }

        .powered-by {
            text-align: center;
            margin-top: 30px;
            color: #888;
            font-size: 14px;
        }

        .powered-by img {
            height: 20px;
            vertical-align: middle;
            margin-left: 5px;
        }

        .bank-select {
            width: 100%;
            padding: 12px;
            border: 1px solid #ddd;
            border-radius: 8px;
            font-size: 16px;
            margin-bottom: 15px;
        }

        .transaction-item {
            background: #f9f9f9;
            padding: 15px;
            border-radius: 8px;
            margin-bottom: 10px;
            display: flex;
            justify-content: space-between;
            font-size: 15px;
            font-family: 'Courier New', monospace;
        }

        .transaction-item .name {
            color: #000;
            font-weight: bold;
        }

        .transaction-item .bank {
            color: #e60000;
            font-weight: bold;
        }

        .transaction-item .amount {
            color: #000;
            font-weight: bold;
        }

        /* BANK TRANSFER PAGE */
        .transfer-header {
            background: #f0f0f0;
            padding: 12px 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-weight: 600;
            color: #333;
            font-size: 16px;
        }

        .transfer-header .cancel {
            color: #e60000;
            cursor: pointer;
        }

        .transfer-content {
            padding: 20px;
            text-align: center;
        }

        .transfer-logo {
            width: 50px;
            height: 50px;
            background: #6a1b9a;
            border-radius: 50%;
            margin: 0 auto 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 24px;
        }

        .transfer-amount {
            font-size: 22px;
            font-weight: bold;
            margin-bottom: 5px;
        }

        .transfer-email {
            color: #666;
            font-size: 14px;
            margin-bottom: 20px;
        }

        .transfer-instruction {
            font-weight: 600;
            margin-bottom: 20px;
            color: #333;
        }

        .transfer-details-box {
            background: #fff;
            border: 1px solid #ddd;
            border-radius: 12px;
            padding: 15px;
            margin-bottom: 20px;
            text-align: left;
        }

        .detail-row {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 12px;
            font-size: 15px;
        }

        .detail-row:last-child {
            margin-bottom: 0;
        }

        .detail-label {
            font-weight: 600;
            color: #333;
        }

        .detail-value {
            font-weight: bold;
            color: #000;
        }

        .copy-btn {
            background: #28a745;
            color: white;
            border: none;
            padding: 4px 10px;
            border-radius: 6px;
            font-size: 12px;
            cursor: pointer;
        }

        .transfer-note {
            font-size: 14px;
            color: #666;
            margin-bottom: 20px;
            text-align: center;
        }

        .btn-transfer {
            background: #28a745;
            color: white;
            width: 100%;
            padding: 16px;
            border: none;
            border-radius: 8px;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
        }
    </style>
</head>
<body>

<!-- LOGIN PAGE -->
<div id="loginPage" class="container">
    <div class="header">EARNERS LOGIN</div>
    <div style="padding:30px;">
        <div class="form-group">
            <label>Username</label>
            <input type="text" id="username" placeholder="Enter username">
        </div>
        <div class="form-group">
            <label>Password</label>
            <input type="password" id="password" placeholder="Enter password">
        </div>
        <div id="loginError" class="error">Wrong password! Buy login</div>
        <button class="btn btn-red" onclick="handleLogin()">Login</button>
        <div class="links">
            <a href="https://whatsapp.com/channel/0029VbCGsFNBadmeC2lxyv3b" target="_blank">Join Whatsapp group</a>
            <a href="#" onclick="showComingSoon()">Watch Video</a>
        </div>
        <div class="coming-soon" id="comingSoon">coming soon</div>
        <a href="#" class="buy-login-link" onclick="showBuyLogin()">Tap here to buy logins!</a>
    </div>
</div>

<!-- SUCCESS LOGIN -->
<div id="successLoginPage" class="container hidden">
    <div class="success-msg">
        <h2>You have successfully logged in.</h2>
        <p>Redirecting to the main page...</p>
    </div>
    <div style="padding:30px;">
        <button class="btn btn-back" onclick="goBack()">Go Back</button>
    </div>
</div>

<!-- DASHBOARD -->
<div id="dashboardPage" class="container hidden">
    <div class="dashboard-header">Instant Earners</div>
    <div class="dashboard-red">
        <button class="dash-btn" onclick="showWithdraw()">
            <div class="icon">+</div>
            <div class="label">Cashout</div>
        </button>
        <button class="dash-btn" onclick="showTransactions()">
            <div class="icon">Refresh</div>
            <div class="label">Transactions</div>
        </button>
    </div>
    <div style="padding:30px;">
        <button class="btn btn-logout" onclick="logout()">Logout</button>
    </div>
</div>

<!-- BUY LOGINS -->
<div id="buyLoginPage" class="container hidden">
    <div class="header">Payment For Logins</div>
    <div style="padding:30px;">
        <p>kindly make your payment to the account provided by flutterwave on the next page you are paying ₦5000</p>
        <div class="form-group" style="margin-top: 30px;">
            <label>Fill in Email to receive logins.</label>
            <input type="email" id="buyEmail" placeholder="Enter your email">
        </div>
        <button class="btn btn-red" onclick="proceedToBuy()">Buy Code</button>
        <button class="btn btn-back" onclick="goBack()">Go Back</button>
    </div>
</div>

<!-- PAYMENT FORM -->
<div id="buyFormPage" class="container hidden">
    <div class="Moh">Instant Earners</div>
    <div style="padding:30px;">
        <div class="form-group">
            <label>Amount</label>
            <input type="text" value="₦5,000" readonly>
        </div>
        <div class="form-group">
            <label>Full Name</label>
            <input type="text" id="fullName" placeholder="Your full name">
        </div>
        <div class="form-group">
            <label>Your Email Address</label>
            <input type="email" id="payerEmail" placeholder="email address">
        </div>
        <button class="btn btn-red" onclick="proceedToTransfer()">Pay</button>
        <div class="powered-by">
            Powered by <img src="https://flutterwave.com/images/logo-colored.svg" alt="flutterwave">
        </div>
        <button class="btn btn-back" onclick="goBack()">Go Back</button>
    </div>
</div>

<!-- BANK TRANSFER PAGE -->
<div id="transferPage" class="container hidden">
    <div class="transfer-header">
        <span>Bank Transfer</span>
        <span class="cancel" onclick="goHome()">Cancel</span>
    </div>
    <div class="transfer-content">
        <div class="transfer-logo">F</div>
        <div class="transfer-amount">NGN 5,000</div>
        <div class="transfer-email">jj86243@gmail.com</div>
        <p class="transfer-instruction">Proceed to your bank app to complete this Transfer</p>

        <div class="transfer-details-box">
            <div class="detail-row">
                <span class="detail-label">Amount</span>
                <span class="detail-value">NGN 5000 <button class="copy-btn" onclick="copyText('5000')">Copy</button></span>
            </div>
            <div class="detail-row">
                <span class="detail-label">Account Number</span>
                <span class="detail-value">8162625816 <button class="copy-btn" onclick="copyText('8162625816')">Copy</button></span>
            </div>
            <div class="detail-row">
                <span class="detail-label">Bank Name</span>
                <span class="detail-value">OPAY LTD</span>
            </div>
            <div class="detail-row">
                <span class="detail-label">Account Name</span>
                <span class="detail-value">QUEEN FUTURE</span>
            </div>
        </div>

        <p class="transfer-note">Pay to this specific account and get your account code</p>
        <button class="btn-transfer" onclick="confirmTransfer()">I have made this bank Transfer</button>
        <button class="btn btn-back" onclick="goBack()">Go Back</button>
    </div>
</div>

<!-- CONFIRMING PAYMENT -->
<div id="confirmingPage" class="container hidden">
    <div class="transfer-header">Bank Transfer</div>
    <div class="transfer-content">
        <div style="text-align:center; margin:40px 0;">
            <div class="spinner"></div>
            <p style="margin-top:20px;">Wait while we confirm your payment...</p>
        </div>
        <button class="btn btn-back" onclick="goBack()">Go Back</button>
    </div>
</div>

<!-- NO PAYMENT CONFIRMED – GO BACK → LOGIN PAGE -->
<div id="noPaymentPage" class="container hidden">
    <div class="success-msg">
        <h2 style="color:#e60000;">No payment confirmed</h2>
    </div>
    <div style="padding:30px;">
        <button class="btn btn-back" onclick="goToLogin()">Go Back</button>
    </div>
</div>

<!-- WITHDRAW PAGE -->
<div id="withdrawPage" class="container hidden">
    <div class="header">Withdraw Funds</div>
    <div style="padding:30px;">
        <div class="form-group">
            <label>Your Name</label>
            <input type="text" id="withdrawName" placeholder="Enter your name">
        </div>
        <div class="form-group">
            <label>Select Bank</label>
            <select class="bank-select" id="bankSelect">
                <option>Palmpay</option>
                <option>OPAY</option>
                <option>Access Bank</option>
                <option>Zenith Bank</option>
                <option>GTBank</option>
                <option>First Bank</option>
                <option>UBA</option>
                <option>Kuda Bank</option>
                <option>Moniepoint</option>
                <option>Fidelity Bank</option>
                <option>Stanbic IBTC</option>
                <option>Union Bank</option>
                <option>Wema Bank</option>
                <option>Sterling Bank</option>
                <option>Ecobank</option>
                <option>Heritage Bank</option>
                <option>Keystone Bank</option>
                <option>Unity Bank</option>
                <option>Polaris Bank</option>
                <option>Providus Bank</option>
                <option>Titan Trust Bank</option>
                <option>Jaiz Bank</option>
                <option>Parallex Bank</option>
                <option>SunTrust Bank</option>
                <option>Globus Bank</option>
                <option>Lotus Bank</option>
                <option>Premium Trust Bank</option>
                <option>Signature Bank</option>
                <option>Taj Bank</option>
                <option>FCMB</option>
                <option>VFD Microfinance Bank</option>
                <option>Carbon</option>
                <option>ALAT by Wema</option>
                <option>Sparkle</option>
                <option>Eyowo</option>
                <option>Rubies Bank</option>
                <option>GoMoney</option>
                <option>Okra</option>
                <option>One Finance</option>
                <option>Paystack</option>
                <option>Flutterwave</option>
                <option>Payoneer</option>
                <option>Remita</option>
                <option>NIP</option>
                <option>Quickteller</option>
                <option>Paga</option>
                <option>Bankly</option>
                <option>Fundall</option>
                <option>Risevest</option>
                <option>Cowrywise</option>
                <option>PiggyVest</option>
                <option>Kuda</option>
                <option>Moniepoint</option>
                <option>Opay</option>
                <option>Palmpay</option>
                <option>9 Payment Service Bank</option>
                <option>Hope PSB</option>
                <option>Momo PSB</option>
                <option>Smartcash PSB</option>
                <option>New Prudential Bank</option>
                <option>Optimise Bank</option>
                <option>Greenlight Bank</option>
                <option>TrustBanc</option>
                <option>Mutual Trust MFB</option>
                <option>Accion MFB</option>
                <option>Addosser MFB</option>
                <option>Advans La Fayette MFB</option>
                <option>Baobab MFB</option>
                <option>Bow Microfinance Bank</option>
                <option>CEMCS MFB</option>
                <option>Corestep MFB</option>
                <option>Credit Direct</option>
                <option>Etranzact</option>
                <option>Fina Trust MFB</option>
                <option>Fortis MFB</option>
                <option>Grooming MFB</option>
                <option>Hasal MFB</option>
                <option>Infinity MFB</option>
                <option>LAPO MFB</option>
                <option>Lovonus MFB</option>
                <option>Manny MFB</option>
                <option>Megapraise MFB</option>
                <option>Mint MFB</option>
                <option>New Golden Pastures MFB</option>
                <option>Page MFB</option>
                <option>Petra MFB</option>
                <option>Renmoney MFB</option>
                <option>Seedvest MFB</option>
                <option>Stanbic IBTC MFB</option>
                <option>Standard Chartered MFB</option>
                <option>TCF MFB</option>
                <option>Teasy Mobile</option>
                <option>Trustfund MFB</option>
                <option>Verite MFB</option>
                <option>VFD MFB</option>
                <option>Zenith MFB</option>
                <option>Access MFB</option>
                <option>First City Monument MFB</option>
                <option>Heritage MFB</option>
                <option>Keystone MFB</option>
                <option>Polaris MFB</option>
                <option>Providus MFB</option>
                <option>Sterling MFB</option>
                <option>Unity MFB</option>c
                <opti        <div class="form-group">
            <label>Amount</label>
            <input type="text" value="₦50,000" readonly>
        </div>
        <button class="btn btn-red" onclick="processWithdraw()">Withdraw</button>
        <button class="btn btn-back" onclick="goBack()">Go Back</button>
    </div>
</div>

<!-- WITHDRAW SUCCESS -->
<div id="withdrawSuccessPage" class="container hidden">
    <div class="success-msg">
        <h2>Withdrawal Successful</h2>
        <p>Your withdrawal has been processed successfully.</p>
        <p><strong>Credited Amount: ₦50,000.00</strong></p>
        <button class="btn btn-red" onclick="goToDashboard()">Go to Dashboard</button>
    </div>
</div>

<!-- TRANSACTIONS PAGE -->
<div id="transactionsPage" class="container hidden">
    <div class="header">Recent Withdrawals</div>
    <div id="transactionsList" style="padding:30px;"></div>
    <div style="padding:0 30px 30px;">
        <button class="btn btn-back" onclick="goToDashboard()">Go Back</button>
    </div>
</div>

<script>
    const CORRECT_PASSWORD = "$2432&";
    let history = ['loginPage'];
    let recentWithdrawals = JSON.parse(localStorage.getItem('recentWithdrawals')) || [];

    const allNames = [
        "Aisha Bello", "Chukwudi Okeke", "Fatima Yusuf", "Emeka Nwosu", "Ngozi Eze",
        "Tunde Adebayo", "Chioma Okafor", "Ibrahim Musa", "Funmi Adeyemi", "Segun Olaniyi",
        "Bola Ahmed", "Kemi Adewale", "Yusuf Lawal", "Adaobi Chukwu", "Olawale Bakare",
        "Mariam Sani", "David Ojo", "Grace Nnamdi", "Suleiman Ali", "Patricia Okonkwo",
        "Victor Eke", "Halima Abdullahi", "Samuel Obi", "Blessing Uche", "Mustapha Garba",
        "Jennifer Ike", "Abdulrahman Danjuma", "Esther Madu", "Kingsley Okoro", "Rukayat Salami",
        "Peter Anya", "Linda Nwachukwu", "Ismaila Bello", "Victoria Akpan", "Hassan Ibrahim",
        "Mercy Ogunleye", "Joseph Ade", "Zainab Mohammed", "Paul Ekwueme", "Roseline Ibe",
        "Ahmed Sani", "Stella Okeke", "Femi Olatunji", "Juliet Nwankwo", "Umar Farouk",
        "Clara Onyeka", "Tope Adekunle", "Aminu Yakubu", "Sandra Eze", "Nasiru Adamu"
    ];

    function getDailyNames() {
        const today = new Date().toDateString();
        let seed = 0;
        for (let i = 0; i < today.length; i++) seed += today.charCodeAt(i);
        const shuffled = [...allNames].sort(() => 0.5 - Math.random());
        return shuffled.slice(0, 15);
    }

    function showPage(id) {
        document.querySelectorAll('.container').forEach(el => el.classList.add('hidden'));
        const page = document.getElementById(id);
        page.classList.remove('hidden');
        if (!history.includes(id)) history.push(id);
    }

    function updateHistory(id) {
        showPage(id);
    }

    function goBack() {
        if (history.length > 1) {
            history.pop();
            showPage(history[history.length - 1]);
        }
    }

    // Direct to Login Page
    function goToLogin() {
        history = ['loginPage'];
        showPage('loginPage');
    }

    function handleLogin() {
        const username = document.getElementById('username').value.trim();
        const password = document.getElementById('password').value;
        const error = document.getElementById('loginError');
        if (password === CORRECT_PASSWORD && username !== "") {
            error.style.display = 'none';
            updateHistory('successLoginPage');
            setTimeout(() => updateHistory('dashboardPage'), 3000);
        } else {
            error.style.display = 'block';
        }
    }

    function showComingSoon() {
        const msg = document.getElementById('comingSoon');
        msg.style.display = 'block';
        setTimeout(() => msg.style.display = 'none', 2000);
    }

    function showBuyLogin() { updateHistory('buyLoginPage'); }
    function showWithdraw() { updateHistory('withdrawPage'); }

    function showTransactions() {
        updateHistory('transactionsPage');
        const list = document.getElementById('transactionsList');
        list.innerHTML = '';
        const dailyNames = getDailyNames();
        const txns = dailyNames.map(name => ({
            name,
            bank: document.getElementById('bankSelect').options[Math.floor(Math.random() * document.getElementById('bankSelect').options.length)].value,
            amount: "₦50,000.00"
        }));
        const allTxns = [...recentWithdrawals, ...txns].slice(0, 20);
        allTxns.forEach(t => {
            list.innerHTML += `
                <div class="transaction-item">
                    <span class="name">${t.name}</span>
                    <span class="bank">${t.bank}</span>
                    <span class="amount">${t.amount}</span>
                </div>`;
        });
    }

    function proceedToBuy() {
        const email = document.getElementById('buyEmail').value;
        if (email.includes('@') && email.includes('.')) updateHistory('buyFormPage');
        else alert("Enter valid email");
    }

    function proceedToTransfer() {
        const name = document.getElementById('fullName').value.trim();
        const email = document.getElementById('payerEmail').value.trim();
        if (name && email.includes('@')) updateHistory('transferPage');
        else alert("Fill all fields");
    }

    function confirmTransfer() {
        updateHistory('confirmingPage');
        setTimeout(() => updateHistory('noPaymentPage'), 20000);
    }

    function goHome() { updateHistory('dashboardPage'); }
    function goToDashboard() { updateHistory('dashboardPage'); }

    function processWithdraw() {
        const name = document.getElementById('withdrawName').value.trim();
        const acc = document.getElementById('accountNumber').value.trim();
        if (name && acc.length >= 10) {
            const bank = document.getElementById('bankSelect').value;
            recentWithdrawals.unshift({ name, bank, amount: "₦50,000.00" });
            if (recentWithdrawals.length > 10) recentWithdrawals.pop();
            localStorage.setItem('recentWithdrawals', JSON.stringify(recentWithdrawals));
            updateHistory('withdrawSuccessPage');
        } else alert("Fill all fields");
    }

    function copyText(text) {
        navigator.clipboard.writeText(text).then(() => alert("Copied: " + text));
    }

    function logout() {
        history = ['loginPage'];
        showPage('loginPage');
        document.getElementById('username').value = '';
        document.getElementById('password').value = '';
        document.getElementById('loginError').style.display = 'none';
    }

    document.getElementById('password').addEventListener('keypress', e => {
        if (e.key === 'Enter') handleLogin();
    });
</script>

</body>
</html>
