<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Zuxxy Services | Payment & Products</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800&display=swap');
        
        :root {
            --primary: #6c5ce7;
            --secondary: #a29bfe;
            --dark: #2d3436;
            --light: #f5f6fa;
            --success: #00b894;
            --danger: #d63031;
            --accent: #fd79a8;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }
        
        body {
            background: url('https://files.catbox.moe/onatx2.jpg') no-repeat center center fixed;
            background-size: cover;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            position: relative;
            overflow-x: hidden;
            color: white;
        }
        
        body::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(45, 52, 54, 0.9), rgba(108, 92, 231, 0.8));
            z-index: 0;
        }
        
        .main-container {
            position: relative;
            z-index: 1;
            width: 95%;
            max-width: 1200px;
            margin: 30px auto;
            display: grid;
            grid-template-columns: 1fr;
            gap: 30px;
        }
        
        .section {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(15px);
            border-radius: 20px;
            padding: 30px;
            box-shadow: 0 25px 45px rgba(0, 0, 0, 0.2);
            border: 1px solid rgba(255, 255, 255, 0.15);
            overflow: hidden;
            animation: fadeInUp 0.8s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }
        
        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .header {
            text-align: center;
            margin-bottom: 30px;
        }
        
        .header h1 {
            font-size: 2.5rem;
            font-weight: 800;
            margin-bottom: 10px;
            background: linear-gradient(to right, var(--accent), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
        }
        
        .header p {
            font-size: 1rem;
            opacity: 0.9;
            font-weight: 300;
        }
        
        .tab-container {
            display: flex;
            justify-content: center;
            margin-bottom: 30px;
        }
        
        .tab-btn {
            background: rgba(255, 255, 255, 0.1);
            border: none;
            color: white;
            padding: 12px 25px;
            margin: 0 10px;
            border-radius: 50px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            gap: 8px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
        }
        
        .tab-btn i {
            font-size: 1.1rem;
        }
        
        .tab-btn.active {
            background: var(--primary);
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(108, 92, 231, 0.4);
        }
        
        .tab-btn:hover:not(.active) {
            background: rgba(255, 255, 255, 0.2);
        }
        
        .tab-content {
            display: none;
            animation: fadeIn 0.5s ease-out;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        
        .tab-content.active {
            display: block;
        }
        
        /* Payment Section Styles */
        .payment-options {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }
        
        .payment-method {
            background: rgba(255, 255, 255, 0.08);
            border-radius: 15px;
            padding: 20px;
            cursor: pointer;
            transition: all 0.4s cubic-bezier(0.25, 0.8, 0.25, 1);
            border: 1px solid rgba(255, 255, 255, 0.05);
            position: relative;
            overflow: hidden;
        }
        
        .payment-method::after {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.1), transparent);
            transition: 0.6s;
        }
        
        .payment-method:hover::after {
            left: 100%;
        }
        
        .payment-method.active {
            background: rgba(255, 255, 255, 0.2);
            border-color: rgba(255, 255, 255, 0.3);
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.2);
        }
        
        .payment-icon {
            width: 50px;
            height: 50px;
            margin-bottom: 15px;
            object-fit: contain;
            filter: drop-shadow(0 2px 5px rgba(0, 0, 0, 0.2));
            transition: transform 0.3s ease;
        }
        
        .payment-method:hover .payment-icon {
            transform: scale(1.1);
        }
        
        .payment-details h3 {
            font-size: 1.1rem;
            font-weight: 600;
            margin-bottom: 5px;
        }
        
        .payment-details p {
            font-size: 0.85rem;
            opacity: 0.8;
            font-weight: 300;
        }
        
        .payment-display {
            background: rgba(0, 0, 0, 0.2);
            border-radius: 15px;
            padding: 30px;
            margin-bottom: 20px;
            text-align: center;
            border: 1px dashed rgba(255, 255, 255, 0.2);
        }
        
        .qris-code {
            width: 100%;
            max-width: 250px;
            margin: 0 auto;
            padding: 15px;
            background: white;
            border-radius: 15px;
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.15);
            transition: all 0.3s ease;
        }
        
        .qris-code:hover {
            transform: scale(1.03);
            box-shadow: 0 12px 30px rgba(0, 0, 0, 0.2);
        }
        
        .qris-code img {
            width: 100%;
            height: auto;
            display: block;
        }
        
        .payment-number {
            margin-top: 15px;
            font-size: 1.2rem;
            font-weight: 500;
            padding: 15px;
            background: rgba(0, 0, 0, 0.3);
            border-radius: 10px;
            display: inline-block;
            position: relative;
            letter-spacing: 1px;
        }
        
        .action-buttons {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-top: 20px;
            flex-wrap: wrap;
        }
        
        .btn {
            padding: 12px 25px;
            border-radius: 50px;
            border: none;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            text-decoration: none;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
        }
        
        .btn-primary {
            background: var(--primary);
            color: white;
        }
        
        .btn-primary:hover {
            background: var(--secondary);
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(108, 92, 231, 0.4);
        }
        
        .btn-secondary {
            background: rgba(255, 255, 255, 0.1);
            color: white;
        }
        
        .btn-secondary:hover {
            background: rgba(255, 255, 255, 0.2);
            transform: translateY(-3px);
        }
        
        .btn i {
            font-size: 1rem;
        }
        
        .payment-instruction {
            color: rgba(255, 255, 255, 0.8);
            font-size: 0.9rem;
            margin-top: 20px;
            line-height: 1.6;
        }
        
        /* Products Section Styles */
        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
        }
        
        .product-card {
            background: rgba(255, 255, 255, 0.08);
            border-radius: 15px;
            padding: 25px;
            transition: all 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.05);
            position: relative;
            overflow: hidden;
        }
        
        .product-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, transparent, rgba(255, 255, 255, 0.03), transparent);
            z-index: -1;
        }
        
        .product-card:hover {
            background: rgba(255, 255, 255, 0.15);
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.2);
        }
        
        .product-title {
            font-size: 1.2rem;
            font-weight: 600;
            margin-bottom: 15px;
            color: var(--accent);
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .product-title i {
            font-size: 1.1rem;
        }
        
        .product-price {
            font-size: 1.1rem;
            font-weight: 700;
            margin-bottom: 15px;
            color: var(--secondary);
        }
        
        .product-features {
            list-style-type: none;
            margin-bottom: 20px;
        }
        
        .product-features li {
            padding: 8px 0;
            border-bottom: 1px dashed rgba(255, 255, 255, 0.1);
            display: flex;
            align-items: center;
            gap: 8px;
        }
        
        .product-features li:last-child {
            border-bottom: none;
        }
        
        .product-features li i {
            color: var(--secondary);
            font-size: 0.8rem;
        }
        
        .whatsapp-channels {
            margin-top: 30px;
            background: rgba(0, 0, 0, 0.2);
            border-radius: 15px;
            padding: 20px;
            text-align: center;
        }
        
        .whatsapp-channels h3 {
            margin-bottom: 15px;
            color: var(--accent);
            font-size: 1.2rem;
        }
        
        .channel-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
        }
        
        .channel-link {
            background: rgba(255, 255, 255, 0.1);
            color: white;
            padding: 12px 20px;
            border-radius: 8px;
            text-decoration: none;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            gap: 8px;
            font-size: 0.9rem;
        }
        
        .channel-link:hover {
            background: var(--success);
            transform: translateY(-3px);
        }
        
        .channel-link i {
            font-size: 1.1rem;
        }
        
        .contact-info {
            margin-top: 40px;
            text-align: center;
        }
        
        .contact-info p {
            margin-bottom: 15px;
            font-size: 1rem;
            color: var(--accent);
            font-weight: 600;
        }
        
        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 20px;
        }
        
        .social-link {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.1);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.3rem;
            transition: all 0.3s ease;
            text-decoration: none;
        }
        
        .social-link:hover {
            transform: translateY(-5px) scale(1.1);
            background: var(--primary);
            box-shadow: 0 8px 20px rgba(108, 92, 231, 0.4);
        }
        
        .footer {
            text-align: center;
            margin-top: 40px;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            font-size: 0.9rem;
            opacity: 0.8;
        }
        
        /* Floating elements */
        .floating-elements {
            position: fixed;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            z-index: -1;
            overflow: hidden;
            pointer-events: none;
        }
        
        .floating-element {
            position: absolute;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            animation: float linear infinite;
        }
        
        @keyframes float {
            0% {
                transform: translateY(0) rotate(0deg);
                opacity: 1;
            }
            100% {
                transform: translateY(-1000px) rotate(720deg);
                opacity: 0;
            }
        }
        
        /* Responsive adjustments */
        @media (max-width: 768px) {
            .main-container {
                grid-template-columns: 1fr;
                gap: 20px;
            }
            
            .section {
                padding: 20px;
            }
            
            .header h1 {
                font-size: 2rem;
            }
            
            .payment-options {
                grid-template-columns: 1fr;
            }
            
            .tab-btn {
                padding: 10px 15px;
                font-size: 0.9rem;
            }
        }
        
        @media (max-width: 480px) {
            .header h1 {
                font-size: 1.8rem;
            }
            
            .tab-container {
                flex-direction: column;
                gap: 10px;
            }
            
            .tab-btn {
                margin: 0;
                width: 100%;
                justify-content: center;
            }
            
            .action-buttons {
                flex-direction: column;
                gap: 10px;
            }
            
            .btn {
                width: 100%;
                justify-content: center;
            }
            
            .channel-links {
                flex-direction: column;
                align-items: center;
            }
        }
    </style>
</head>
<body>
    <div class="floating-elements">
        <!-- Floating elements will be added by JavaScript -->
    </div>
    
    <div class="main-container">
        <div class="section">
            <div class="header">
                <h1>Zuxxy Services</h1>
                <p>Premium hosting and bug solutions</p>
            </div>
            
            <div class="tab-container">
                <button class="tab-btn active" data-tab="payment">
                    <i class="fas fa-money-bill-wave"></i> Payment
                </button>
                <button class="tab-btn" data-tab="products">
                    <i class="fas fa-shopping-bag"></i> Products
                </button>
            </div>
            
            <div class="tab-content active" id="payment-tab">
                <div class="payment-options">
                    <div class="payment-method active" data-method="qris">
                        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/d/d0/QR_code_for_mobile_English_Wikipedia.svg/1200px-QR_code_for_mobile_English_Wikipedia.svg.png" alt="QRIS" class="payment-icon">
                        <div class="payment-details">
                            <h3>QRIS Payment</h3>
                            <p>Scan the QR code below</p>
                        </div>
                    </div>
                    
                    <div class="payment-method" data-method="dana">
                        <img src="https://upload.wikimedia.org/wikipedia/commons/7/72/Logo_DANA.svg" alt="DANA" class="payment-icon">
                        <div class="payment-details">
                            <h3>DANA Wallet</h3>
                            <p>Transfer to DANA number</p>
                        </div>
                    </div>
                    
                    <div class="payment-method" data-method="ovo">
                        <img src="https://upload.wikimedia.org/wikipedia/commons/e/eb/Logo_ovo.svg" alt="OVO" class="payment-icon">
                        <div class="payment-details">
                            <h3>OVO Cash</h3>
                            <p>Transfer to OVO number</p>
                        </div>
                    </div>
                    
                    <div class="payment-method" data-method="gopay">
                        <img src="https://upload.wikimedia.org/wikipedia/commons/8/86/Gopay_logo.svg" alt="GoPay" class="payment-icon">
                        <div class="payment-details">
                            <h3>GoPay</h3>
                            <p>Transfer to GoPay number</p>
                        </div>
                    </div>
                </div>
                
                <div class="payment-display" id="paymentDisplay">
                    <!-- Content will be dynamically updated by JavaScript -->
                </div>
                
                <div class="action-buttons">
                    <button class="btn btn-primary" id="copyBtn">
                        <i class="fas fa-copy"></i> Copy Payment Info
                    </button>
                    <a href="#products-tab" class="btn btn-secondary" id="viewProductsBtn">
                        <i class="fas fa-eye"></i> View Products
                    </a>
                </div>
                
                <p class="payment-instruction">
                    After making payment, please confirm by contacting us via WhatsApp or Telegram with your payment proof.
                </p>
            </div>
            
            <div class="tab-content" id="products-tab">
                <h2 style="text-align: center; margin-bottom: 30px; color: var(--accent);">Our Premium Services</h2>
                
                <div class="products-grid">
                    <div class="product-card">
                        <h3 class="product-title"><i class="fas fa-user-cog"></i> Admin WhatsApp</h3>
                        <div class="product-price">Rp 7.000</div>
                        <ul class="product-features">
                            <li><i class="fas fa-check"></i> Full admin access</li>
                            <li><i class="fas fa-check"></i> WhatsApp integration</li>
                            <li><i class="fas fa-check"></i> Easy management</li>
                        </ul>
                    </div>
                    
                    <div class="product-card">
                        <h3 class="product-title"><i class="fas fa-server"></i> MURBUG VIA TELE</h3>
                        <div class="product-price">Rp 10.000</div>
                        <ul class="product-features">
                            <li><i class="fas fa-check"></i> Affordable bug via Telegram</li>
                            <li><i class="fas fa-check"></i> Easy to use</li>
                            <li><i class="fas fa-check"></i> Quick setup</li>
                        </ul>
                    </div>
                    
                    <div class="product-card">
                        <h3 class="product-title"><i class="fas fa-gamepad"></i> PANEL PTERODACTYL</h3>
                        <div class="product-price">Rp 1.000 - Rp 11.000</div>
                        <ul class="product-features">
                            <li><i class="fas fa-check"></i> 1 to Unlimited slots</li>
                            <li><i class="fas fa-check"></i> High performance</li>
                            <li><i class="fas fa-check"></i> Reliable hosting</li>
                        </ul>
                    </div>
                    
                    <div class="product-card">
                        <h3 class="product-title"><i class="fas fa-user-shield"></i> ADMIN MURBUG TELE</h3>
                        <div class="product-price">Rp 15.000</div>
                        <ul class="product-features">
                            <li><i class="fas fa-check"></i> Full admin access</li>
                            <li><i class="fas fa-check"></i> Telegram integration</li>
                            <li><i class="fas fa-check"></i> Secure connection</li>
                        </ul>
                    </div>
                    
                    <div class="product-card">
                        <h3 class="product-title"><i class="fas fa-code"></i> SC BUG VIA WA</h3>
                        <div class="product-price">Rp 10.000 - Rp 20.000</div>
                        <ul class="product-features">
                            <li><i class="fas fa-check"></i> Encrypted (Rp 20k)</li>
                            <li><i class="fas fa-check"></i> Non-encrypted (Rp 10k)</li>
                            <li><i class="fas fa-check"></i> WhatsApp delivery</li>
                        </ul>
                    </div>
                    
                    <div class="product-card">
                        <h3 class="product-title"><i class="fas fa-terminal"></i> ADMIN PANEL</h3>
                        <div class="product-price">Rp 15.000</div>
                        <ul class="product-features">
                            <li><i class="fas fa-check"></i> R16C4 Private specs</li>
                            <li><i class="fas fa-check"></i> Full control</li>
                            <li><i class="fas fa-check"></i> High performance</li>
                        </ul>
                    </div>
                    
                    <div class="product-card">
                        <h3 class="product-title"><i class="fas fa-tools"></i> JASA FIX SC</h3>
                        <div class="product-price">Rp 5.000/SC</div>
                        <ul class="product-features">
                            <li><i class="fas fa-check"></i> Script fixing</li>
                            <li><i class="fas fa-check"></i> Quick turnaround</li>
                            <li><i class="fas fa-check"></i> Expert solution</li>
                        </ul>
                    </div>
                    
                    <div class="product-card">
                        <h3 class="product-title"><i class="fas fa-file-signature"></i> JASA RENAME</h3>
                        <div class="product-price">Rp 5.000/SC</div>
                        <ul class="product-features">
                            <li><i class="fas fa-check"></i> Custom naming</li>
                            <li><i class="fas fa-check"></i> Quick service</li>
                            <li><i class="fas fa-check"></i> Professional work</li>
                        </ul>
                    </div>
                    
                    <div class="product-card">
                        <h3 class="product-title"><i class="fas fa-bug"></i> JASA WAR BUG</h3>
                        <div class="product-price">Rp 10.000+</div>
                        <ul class="product-features">
                            <li><i class="fas fa-check"></i> Depending on difficulty</li>
                            <li><i class="fas fa-check"></i> Expert solution</li>
                            <li><i class="fas fa-check"></i> Custom work</li>
                        </ul>
                    </div>
                </div>
                
                <div class="whatsapp-channels">
                    <h3><i class="fab fa-whatsapp"></i> WhatsApp Channels</h3>
                    <div class="channel-links">
                        <a href="https://whatsapp.com/channel/0029Vb0lwloJpe8gB6tJ9l3t" class="channel-link" target="_blank">
                            <i class="fas fa-code"></i> Script Free
                        </a>
                        <a href="https://whatsapp.com/channel/0029VbApT2VLY6d8X3OQEd3a" class="channel-link" target="_blank">
                            <i class="fas fa-star"></i> Testimoni
                        </a>
                    </div>
                </div>
                
                <div class="contact-info">
                    <p>Interested? Contact us now!</p>
                    <div class="social-links">
                        <a href="https://wa.me/628317668145" class="social-link" target="_blank">
                            <i class="fab fa-whatsapp"></i>
                        </a>
                        <a href="https://t.me/alwayszuxxy" class="social-link" target="_blank">
                            <i class="fab fa-telegram"></i>
                        </a>
                    </div>
                </div>
                
                <div class="footer">
                    Payment By Always Zuxxy
                </div>
            </div>
        </div>
    </div>
    
        <script>
        // Create floating elements
        const floatingContainer = document.querySelector('.floating-elements');
        const elementCount = 20;
        
        for (let i = 0; i < elementCount; i++) {
            const element = document.createElement('div');
            element.classList.add('floating-element');
            
            // Random size between 5px and 20px
            const size = Math.random() * 15 + 5;
            element.style.width = `${size}px`;
            element.style.height = `${size}px`;
            
            // Random position
            element.style.left = `${Math.random() * 100}%`;
            
            // Random animation duration between 15s and 30s
            const duration = Math.random() * 15 + 15;
            element.style.animationDuration = `${duration}s`;
            
            // Random delay
            element.style.animationDelay = `${Math.random() * 10}s`;
            
            // Random shape (circle or square)
            if (Math.random() > 0.7) {
                element.style.borderRadius = '3px';
            }
            
            floatingContainer.appendChild(element);
        }
        
        // Payment methods data
        const paymentMethods = {
            qris: {
                type: 'qris',
                image: 'https://files.catbox.moe/9ghz41.jpg',
                instruction: 'Scan this QR code using your mobile banking app or e-wallet',
                data: 'https://files.catbox.moe/9ghz41.jpg'
            },
            dana: {
                type: 'number',
                number: '089518493307',
                instruction: 'Send payment to this DANA number via DANA app',
                data: '089518493307'
            },
            ovo: {
                type: 'number',
                number: '082147321612',
                instruction: 'Send payment to this OVO number via OVO app',
                data: '082147321612'
            },
            gopay: {
                type: 'number',
                number: '082147321612',
                instruction: 'Send payment to this GoPay number via GoJek app',
                data: '082147321612'
            }
        };
        
        // Tab functionality
        const tabBtns = document.querySelectorAll('.tab-btn');
        const tabContents = document.querySelectorAll('.tab-content');
        
        tabBtns.forEach(btn => {
            btn.addEventListener('click', () => {
                const tabId = btn.getAttribute('data-tab');
                
                // Update active tab button
                tabBtns.forEach(b => b.classList.remove('active'));
                btn.classList.add('active');
                
                // Update active tab content
                tabContents.forEach(content => content.classList.remove('active'));
                document.getElementById(`${tabId}-tab`).classList.add('active');
            });
        });
        
        // View products button
        document.getElementById('viewProductsBtn').addEventListener('click', (e) => {
            if (e.target.tagName === 'A') {
                e.preventDefault();
                const targetTab = document.querySelector(e.target.getAttribute('href'));
                
                tabBtns.forEach(b => b.classList.remove('active'));
                document.querySelector('.tab-btn[data-tab="products"]').classList.add('active');
                
                tabContents.forEach(content => content.classList.remove('active'));
                targetTab.classList.add('active');
                
                // Smooth scroll to products section
                targetTab.scrollIntoView({ behavior: 'smooth' });
            }
        });
        
        // Payment method selection
        const methodElements = document.querySelectorAll('.payment-method');
        const paymentDisplay = document.getElementById('paymentDisplay');
        const copyBtn = document.getElementById('copyBtn');
        let currentMethod = 'qris';
        
        function updatePaymentDisplay(method) {
            const data = paymentMethods[method];
            currentMethod = method;
            let html = '';
            
            if (data.type === 'qris') {
                html = `
                    <div class="qris-code">
                        <img src="${data.image}" alt="QRIS Code">
                    </div>
                    <p class="payment-instruction">${data.instruction}</p>
                `;
                copyBtn.innerHTML = '<i class="fas fa-copy"></i> Copy QRIS Link';
            } else {
                html = `
                    <div class="payment-number">
                        ${data.number}
                    </div>
                    <p class="payment-instruction">${data.instruction}</p>
                `;
                copyBtn.innerHTML = '<i class="fas fa-copy"></i> Copy Number';
            }
            
            paymentDisplay.innerHTML = html;
            paymentDisplay.style.animation = 'none';
            void paymentDisplay.offsetWidth; // Trigger reflow
            paymentDisplay.style.animation = 'fadeIn 0.5s ease-out';
        }
        
        // Add click event to payment methods
        methodElements.forEach(method => {
            method.addEventListener('click', () => {
                // Remove active class from all methods
                methodElements.forEach(m => m.classList.remove('active'));
                
                // Add active class to clicked method
                method.classList.add('active');
                
                // Update payment display
                const methodName = method.getAttribute('data-method');
                updatePaymentDisplay(methodName);
            });
        });
        
        // Copy button functionality
        copyBtn.addEventListener('click', () => {
            const data = paymentMethods[currentMethod];
            
            if (data.type === 'qris') {
                // For QRIS, copy the image URL
                navigator.clipboard.writeText(data.image).then(() => {
                    copyBtn.innerHTML = '<i class="fas fa-check"></i> Link Copied!';
                    setTimeout(() => {
                        copyBtn.innerHTML = '<i class="fas fa-copy"></i> Copy QRIS Link';
                    }, 2000);
                });
            } else {
                // For numbers, copy the number
                navigator.clipboard.writeText(data.number).then(() => {
                    copyBtn.innerHTML = '<i class="fas fa-check"></i> Number Copied!';
                    setTimeout(() => {
                        copyBtn.innerHTML = '<i class="fas fa-copy"></i> Copy Number';
                    }, 2000);
                });
            }
        });
        
        // Initialize with QRIS active
        document.addEventListener('DOMContentLoaded', () => {
            updatePaymentDisplay('qris');
        });
    </script>
</body>
</html>
