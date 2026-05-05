<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>🍽️ Vencher Food Store - Delicious Food, Delivered Fast!</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&family=Nunito:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Nunito', sans-serif;
            background: linear-gradient(135deg, #FFF8F0 0%, #FFF2E8 100%);
            color: #3D1C02;
            overflow-x: hidden;
            line-height: 1.6;
        }

        /* Navbar */
        .navbar {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(255, 248, 240, 0.95);
            backdrop-filter: blur(20px);
            z-index: 1000;
            padding: 1rem 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 2px 20px rgba(255, 107, 53, 0.1);
            transition: all 0.3s ease;
        }

        .logo {
            font-family: 'Poppins', sans-serif;
            font-size: 1.8rem;
            font-weight: 700;
            background: linear-gradient(135deg, #FF6B35, #FFD700);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            text-decoration: none;
            color: #3D1C02;
            font-weight: 500;
            transition: color 0.3s ease;
            position: relative;
        }

        .nav-links a:hover {
            color: #FF6B35;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: -5px;
            left: 0;
            background: linear-gradient(135deg, #FF6B35, #FFD700);
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .nav-actions {
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .cart-btn {
            position: relative;
            background: linear-gradient(135deg, #FF6B35, #FFD700);
            color: white;
            border: none;
            padding: 0.8rem 1.2rem;
            border-radius: 50px;
            cursor: pointer;
            font-size: 1.1rem;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(255, 107, 53, 0.3);
        }

        .cart-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(255, 107, 53, 0.4);
        }

        .cart-count {
            position: absolute;
            top: -8px;
            right: -8px;
            background: #C1121F;
            color: white;
            border-radius: 50%;
            width: 24px;
            height: 24px;
            font-size: 0.8rem;
            font-weight: 600;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .auth-btn {
            background: transparent;
            border: 2px solid #FF6B35;
            color: #FF6B35;
            padding: 0.6rem 1.2rem;
            border-radius: 25px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .auth-btn:hover {
            background: #FF6B35;
            color: white;
            transform: translateY(-1px);
        }

        .user-profile {
            background: linear-gradient(135deg, #FF6B35, #FFD700);
            color: white;
            padding: 0.6rem 1.2rem;
            border-radius: 25px;
            font-weight: 600;
            cursor: pointer;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            background: linear-gradient(135deg, 
                rgba(255, 107, 53, 0.9) 0%, 
                rgba(255, 215, 0, 0.8) 50%,
                rgba(193, 18, 31, 0.9) 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '🍕🍔🍜🍗🍰🥗';
            position: absolute;
            font-size: 4rem;
            animation: float 20s infinite linear;
            top: 20%;
            left: -20%;
        }

        @keyframes float {
            0% { transform: translateX(-100%) translateY(0); }
            100% { transform: translateX(100vw) translateY(50px); }
        }

        .hero-content h1 {
            font-family: 'Poppins', sans-serif;
            font-size: clamp(3rem, 8vw, 6rem);
            font-weight: 700;
            margin-bottom: 1rem;
            animation: slideInUp 1s ease-out;
        }

        .hero-content p {
            font-size: clamp(1.2rem, 3vw, 1.8rem);
            margin-bottom: 2rem;
            animation: slideInUp 1s ease-out 0.2s both;
        }

        .cta-btn {
            background: linear-gradient(135deg, #FFD700, #FF6B35);
            color: #3D1C02;
            padding: 1.2rem 3rem;
            font-size: 1.3rem;
            font-weight: 700;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 8px 30px rgba(255, 215, 0, 0.4);
            animation: slideInUp 1s ease-out 0.4s both;
        }

        .cta-btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 12px 40px rgba(255, 215, 0, 0.6);
        }

        @keyframes slideInUp {
            from {
                opacity: 0;
                transform: translateY(50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Sections */
        section {
            padding: 100px 5%;
            max-width: 1400px;
            margin: 0 auto;
        }

        h2 {
            font-family: 'Poppins', sans-serif;
            font-size: 3rem;
            text-align: center;
            margin-bottom: 3rem;
            background: linear-gradient(135deg, #FF6B35, #FFD700);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        /* Categories */
        .categories {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
            margin-bottom: 4rem;
        }

        .category-card {
            background: white;
            padding: 2rem;
            border-radius: 20px;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            border: 3px solid transparent;
        }

        .category-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 50px rgba(255, 107, 53, 0.3);
            border-color: #FF6B35;
        }

        .category-card i {
            font-size: 3rem;
            margin-bottom: 1rem;
            background: linear-gradient(135deg, #FF6B35, #FFD700);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .category-card.active {
            background: linear-gradient(135deg, #FF6B35, #FFD700);
            color: white;
        }

        /* Menu Items */
        .menu-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .food-card {
            background: white;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 15px 40px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
            position: relative;
        }

        .food-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 25px 60px rgba(255, 107, 53, 0.3);
        }

        .food-image {
            height: 200px;
            background: linear-gradient(135deg, #FF6B35, #FFD700);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
            position: relative;
        }

        .food-info {
            padding: 1.5rem;
        }

        .food-name {
            font-family: 'Poppins', sans-serif;
            font-size: 1.4rem;
            font-weight: 600;
            margin-bottom: 0.5rem;
        }

        .food-desc {
            color: #666;
            margin-bottom: 1rem;
            font-size: 0.95rem;
        }

        .food-price {
            font-size: 1.3rem;
            font-weight: 700;
            color: #C1121F;
            margin-bottom: 1rem;
        }

        .stars {
            color: #FFD700;
            margin-bottom: 1rem;
        }

        .add-btn {
            width: 100%;
            background: linear-gradient(135deg, #FF6B35, #FFD700);
            color: #3D1C02;
            border: none;
            padding: 0.8rem;
            border-radius: 10px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .add-btn:hover {
            transform: scale(1.05);
        }

        /* Cart Modal */
        .cart-modal {
            position: fixed;
            top: 0;
            right: -100%;
            width: 400px;
            height: 100vh;
            background: white;
            box-shadow: -5px 0 30px rgba(0,0,0,0.2);
            transition: right 0.3s ease;
            z-index: 2000;
            overflow-y: auto;
        }

        .cart-modal.active {
            right: 0;
        }

        .cart-header {
            padding: 2rem;
            border-bottom: 1px solid #eee;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .close-cart {
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
            color: #FF6B35;
        }

        .cart-item {
            display: flex;
            padding: 1.5rem 2rem;
            border-bottom: 1px solid #eee;
            gap: 1rem;
        }

        .cart-item-image {
            width: 60px;
            height: 60px;
            border-radius: 10px;
            background: linear-gradient(135deg, #FF6B35, #FFD700);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
        }

        .cart-item-info h4 {
            margin-bottom: 0.5rem;
        }

        .quantity-controls {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            margin: 0.5rem 0;
        }

        .qty-btn {
            width: 30px;
            height: 30px;
            border: 1px solid #FF6B35;
            background: white;
            border-radius: 50%;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .cart-total {
            padding: 2rem;
            border-top: 3px solid #FF6B35;
        }

        .total-row {
            display: flex;
            justify-content: space-between;
            margin-bottom: 0.5rem;
            font-weight: 600;
        }

        .grand-total {
            font-size: 1.5rem;
            color: #C1121F;
        }

        .checkout-btn {
            width: 100%;
            background: linear-gradient(135deg, #FF6B35, #C1121F);
            color: white;
            border: none;
            padding: 1rem;
            border-radius: 10px;
            font-size: 1.1rem;
            font-weight: 600;
            cursor: pointer;
            margin-top: 1rem;
        }

        /* Auth Modal */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.5);
            z-index: 1500;
            display: none;
            align-items: center;
            justify-content: center;
        }

        .modal-overlay.active {
            display: flex;
        }

        .auth-modal {
            background: white;
            padding: 3rem;
            border-radius: 20px;
            max-width: 400px;
            width: 90%;
            box-shadow: 0 20px 60px rgba(0,0,0,0.3);
            animation: modalSlideIn 0.3s ease;
        }

        @keyframes modalSlideIn {
            from {
                opacity: 0;
                transform: scale(0.8) translateY(-20px);
            }
            to {
                opacity: 1;
                transform: scale(1) translateY(0);
            }
        }

        .modal-tabs {
            display: flex;
            margin-bottom: 2rem;
            border-bottom: 2px solid #eee;
        }

        .tab-btn {
            flex: 1;
            padding: 1rem;
            background: none;
            border: none;
            font-weight: 600;
            cursor: pointer;
            transition: color 0.3s ease;
        }

        .tab-btn.active {
            color: #FF6B35;
            border-bottom: 3px solid #FF6B35;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 600;
        }

        .form-group input {
            width: 100%;
            padding: 1rem;
            border: 2px solid #eee;
            border-radius: 10px;
            font-size: 1rem;
            transition: border-color 0.3s ease;
        }

        .form-group input:focus {
            outline: none;
            border-color: #FF6B35;
        }

        .submit-btn {
            width: 100%;
            background: linear-gradient(135deg, #FF6B35, #FFD700);
            color: #3D1C02;
            border: none;
            padding: 1rem;
            border-radius: 10px;
            font-size: 1.1rem;
            font-weight: 600;
            cursor: pointer;
        }

        /* Order Form */
        .order-form {
            display: none;
            max-width: 500px;
            margin: 2rem auto;
            background: white;
            padding: 3rem;
            border-radius: 20px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.1);
        }

        .order-form.active {
            display: block;
            animation: slideInUp 0.5s ease;
        }

        /* Toast */
        .toast {
            position: fixed;
            bottom: 30px;
            right: 30px;
            background: linear-gradient(135deg, #FF6B35, #FFD700);
            color: #3D1C02;
            padding: 1rem 2rem;
            border-radius: 50px;
            font-weight: 600;
            transform: translateX(400px);
            transition: transform 0.3s ease;
            z-index: 3000;
            box-shadow: 0 10px 30px rgba(255, 107, 53, 0.4);
        }

        .toast.show {
            transform: translateX(0);
        }

        /* About & Contact */
        .features {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .feature-card {
            text-align: center;
            padding: 2rem;
            background: white;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }

        .feature-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
        }

        .contact-info {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-bottom: 3rem;
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 1rem;
            padding: 1.5rem;
            background: white;
            border-radius: 15px;
            box-shadow: 0 5px 20px rgba(0,0,0,0.1);
        }

        /* Footer */
        .footer {
            background: #3D1C02;
            color: white;
            padding: 4rem 5% 2rem;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-bottom: 2rem;
        }

        .footer-section h3 {
            margin-bottom: 1rem;
            color: #FFD700;
        }

        .social-links {
            display: flex;
            gap: 1rem;
        }

        .social-links a {
            color: white;
            font-size: 1.5rem;
            transition: color 0.3s ease;
        }

        .social-links a:hover {
            color: #FF6B35;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .navbar {
                padding: 1rem 3%;
            }

            .nav-links {
                display: none;
            }

            .cart-modal {
                width: 100%;
            }

            section {
                padding: 80px 3%;
            }

            h2 {
                font-size: 2rem;
            }
        }

        /* Smooth Scroll */
        html {
            scroll-behavior: smooth;
        }

        /* Hidden class */
        .hidden {
            display: none !important;
        }
    </style>
</head>
<body>
    <!-- Navbar -->
    <nav class="navbar">
        <div class="logo">🍽️ Vencher Food Store</div>
        <ul class="nav-links">
            <li><a href="#home">Home</a></li>
            <li><a href="#menu">Menu</a></li>
            <li><a href="#about">About</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
        <div class="nav-actions">
            <button class="cart-btn" onclick="toggleCart()">
                <i class="fas fa-shopping-cart"></i>
                <span class="cart-count" id="cartCount">0</span>
            </button>
            <div id="userAuth">
                <button class="auth-btn" onclick="openAuthModal()">Login</button>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="hero-content">
            <h1>Delicious Food,<br>Delivered Fast! 🚀</h1>
            <p>Order from your favorite restaurants with just a few taps</p>
            <button class="cta-btn" onclick="scrollToMenu()">Order Now 🍕</button>
        </div>
    </section>

    <!-- Categories -->
    <section id="menu" class="categories-section">
        <h2>🍽️ Choose Your Craving</h2>
        <div class="categories" id="categories">
            <!-- Categories will be populated by JS -->
        </div>

        <!-- Menu Items -->
        <h2 style="margin-top: 4rem;">Our Delicious Menu</h2>
        <div class="menu-grid" id="menuGrid">
            <!-- Menu items will be populated by JS -->
        </div>
    </section>

    <!-- About Section -->
    <section id="about">
        <h2>👨‍🍳 About Vencher</h2>
        <div class="features">
            <div class="feature-card">
                <div class="feature-icon">🚀</div>
                <h3>Lightning Fast Delivery</h3>
                <p>Get your food delivered in under 30 minutes!</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">🥦</div>
                <h3>100% Fresh Ingredients</h3>
                <p>Only
