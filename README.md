<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PZ Furniture | Premium Furniture & Interior Design</title>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;600;700&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #1a1a1a;
            --secondary: #c9a962;
            --accent: #8b7355;
            --light: #f5f5f0;
            --white: #ffffff;
            --gray: #666666;
            --transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', sans-serif;
            color: var(--primary);
            line-height: 1.6;
            overflow-x: hidden;
        }

        h1, h2, h3, h4 {
            font-family: 'Playfair Display', serif;
            font-weight: 600;
        }

        nav {
            position: fixed;
            top: 0;
            width: 100%;
            padding: 20px 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 1000;
            transition: var(--transition);
            background: transparent;
        }

        nav.scrolled {
            background: var(--white);
            box-shadow: 0 2px 20px rgba(0,0,0,0.1);
            padding: 15px 5%;
        }

        .logo {
            font-family: 'Playfair Display', serif;
            font-size: 2rem;
            font-weight: 700;
            color: var(--white);
            text-decoration: none;
            transition: var(--transition);
        }

        nav.scrolled .logo {
            color: var(--primary);
        }

        .nav-links {
            display: flex;
            gap: 40px;
            list-style: none;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--white);
            font-weight: 500;
            font-size: 0.95rem;
            transition: var(--transition);
            position: relative;
        }

        nav.scrolled .nav-links a {
            color: var(--primary);
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--secondary);
            transition: var(--transition);
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .mobile-menu {
            display: none;
            flex-direction: column;
            gap: 5px;
            cursor: pointer;
        }

        .mobile-menu span {
            width: 25px;
            height: 2px;
            background: var(--white);
            transition: var(--transition);
        }

        nav.scrolled .mobile-menu span {
            background: var(--primary);
        }

        .hero {
            height: 100vh;
            background: linear-gradient(135deg, rgba(26,26,26,0.8), rgba(26,26,26,0.6)), #1a1a1a;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            position: relative;
        }

        .hero-content {
            max-width: 900px;
            padding: 0 20px;
            animation: fadeInUp 1s ease;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .hero h1 {
            font-size: clamp(2.5rem, 6vw, 4.5rem);
            color: var(--white);
            margin-bottom: 20px;
            line-height: 1.2;
        }

        .hero h1 span {
            color: var(--secondary);
        }

        .hero p {
            font-size: 1.2rem;
            color: rgba(255,255,255,0.9);
            margin-bottom: 40px;
            font-weight: 300;
        }

        .cta-buttons {
            display: flex;
            gap: 20px;
            justify-content: center;
            flex-wrap: wrap;
        }

        .btn {
            padding: 15px 40px;
            text-decoration: none;
            font-weight: 600;
            transition: var(--transition);
            border-radius: 0;
            text-transform: uppercase;
            letter-spacing: 1px;
            font-size: 0.9rem;
        }

        .btn-primary {
            background: var(--secondary);
            color: var(--primary);
            border: 2px solid var(--secondary);
        }

        .btn-primary:hover {
            background: transparent;
            color: var(--secondary);
        }

        .btn-secondary {
            background: transparent;
            color: var(--white);
            border: 2px solid var(--white);
        }

        .btn-secondary:hover {
            background: var(--white);
            color: var(--primary);
        }

        section {
            padding: 100px 5%;
        }

        .section-header {
            text-align: center;
            margin-bottom: 60px;
        }

        .section-header h2 {
            font-size: clamp(2rem, 4vw, 3rem);
            margin-bottom: 15px;
            position: relative;
            display: inline-block;
        }

        .section-header h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 60px;
            height: 3px;
            background: var(--secondary);
        }

        .section-header p {
            color: var(--gray);
            max-width: 600px;
            margin: 20px auto 0;
        }

        .about {
            background: var(--light);
        }

        .about-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: center;
            max-width: 1200px;
            margin: 0 auto;
        }

        .about-image {
            position: relative;
            overflow: hidden;
        }

        .about-image::before {
            content: '';
            position: absolute;
            top: -20px;
            left: -20px;
            width: 100%;
            height: 100%;
            border: 3px solid var(--secondary);
            z-index: -1;
        }

        .about-image-placeholder {
            width: 100%;
            height: 500px;
            background: linear-gradient(135deg, var(--primary), var(--accent));
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--white);
            font-size: 1.2rem;
        }

        .about-content h3 {
            font-size: 2rem;
            margin-bottom: 20px;
        }

        .about-content p {
            margin-bottom: 20px;
            color: var(--gray);
        }

        .features {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 20px;
            margin-top: 30px;
        }

        .feature {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .feature-icon {
            width: 40px;
            height: 40px;
            background: var(--secondary);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--primary);
            font-weight: bold;
        }

        .products {
            background: var(--white);
        }

        .product-categories {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin-bottom: 50px;
            flex-wrap: wrap;
        }

        .category-btn {
            padding: 10px 25px;
            border: 2px solid var(--primary);
            background: transparent;
            cursor: pointer;
            font-family: 'Inter', sans-serif;
            font-weight: 500;
            transition: var(--transition);
        }

        .category-btn.active,
        .category-btn:hover {
            background: var(--primary);
            color: var(--white);
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            max-width: 1400px;
            margin: 0 auto;
        }

        .product-card {
            position: relative;
            overflow: hidden;
            cursor: pointer;
        }

        .product-image {
            width: 100%;
            height: 400px;
            background: linear-gradient(135deg, #e0e0e0, #f0f0f0);
            position: relative;
            overflow: hidden;
            transition: var(--transition);
        }

        .product-card:hover .product-image {
            transform: scale(1.05);
        }

        .product-overlay {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: linear-gradient(to top, rgba(26,26,26,0.9), transparent);
            padding: 30px;
            color: var(--white);
            transform: translateY(20px);
            opacity: 0;
            transition: var(--transition);
        }

        .product-card:hover .product-overlay {
            transform: translateY(0);
            opacity: 1;
        }

        .product-info {
            padding: 20px;
            background: var(--white);
        }

        .product-info h3 {
            font-size: 1.3rem;
            margin-bottom: 5px;
        }

        .product-info p {
            color: var(--gray);
            font-size: 0.9rem;
        }

        .price {
            color: var(--secondary);
            font-weight: 600;
            font-size: 1.1rem;
            margin-top: 10px;
        }

        .services {
            background: var(--primary);
            color: var(--white);
        }

        .services .section-header h2 {
            color: var(--white);
        }

        .services .section-header p {
            color: rgba(255,255,255,0.7);
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .service-card {
            text-align: center;
            padding: 40px 30px;
            border: 1px solid rgba(201,169,98,0.3);
            transition: var(--transition);
            position: relative;
            overflow: hidden;
        }

        .service-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: var(--secondary);
            transition: var(--transition);
            z-index: -1;
        }

        .service-card:hover::before {
            left: 0;
        }

        .service-card:hover {
            color: var(--primary);
            transform: translateY(-10px);
        }

        .service-icon {
            font-size: 3rem;
            margin-bottom: 20px;
            color: var(--secondary);
        }

        .service-card:hover .service-icon {
            color: var(--primary);
        }

        .service-card h3 {
            font-size: 1.3rem;
            margin-bottom: 15px;
        }

        .contact {
            background: var(--light);
        }

        .contact-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .contact-info h3 {
            font-size: 2rem;
            margin-bottom: 30px;
        }

        .contact-details {
            margin-bottom: 40px;
        }

        .contact-item {
            display: flex;
            align-items: flex-start;
            gap: 20px;
            margin-bottom: 25px;
        }

        .contact-icon {
            width: 50px;
            height: 50px;
            background: var(--secondary);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2rem;
            color: var(--primary);
            flex-shrink: 0;
        }

        .contact-item h4 {
            margin-bottom: 5px;
            font-size: 1.1rem;
        }

        .contact-item p {
            color: var(--gray);
        }

        .contact-form {
            background: var(--white);
            padding: 50px;
            box-shadow: 0 10px 40px rgba(0,0,0,0.1);
        }

        .form-group {
            margin-bottom: 25px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
            color: var(--primary);
        }

        .form-group input,
        .form-group textarea,
        .form-group select {
            width: 100%;
            padding: 15px;
            border: 1px solid #ddd;
            font-family: 'Inter', sans-serif;
            transition: var(--transition);
        }

        .form-group input:focus,
        .form-group textarea:focus,
        .form-group select:focus {
            outline: none;
            border-color: var(--secondary);
        }

        .form-group textarea {
            resize: vertical;
            min-height: 120px;
        }

        .submit-btn {
            width: 100%;
            padding: 18px;
            background: var(--primary);
            color: var(--white);
            border: none;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
            cursor: pointer;
            transition: var(--transition);
        }

        .submit-btn:hover {
            background: var(--secondary);
            color: var(--primary);
        }

        footer {
            background: var(--primary);
            color: var(--white);
            padding: 60px 5% 30px;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
            max-width: 1200px;
            margin: 0 auto 40px;
        }

        .footer-section h4 {
            color: var(--secondary);
            margin-bottom: 20px;
            font-size: 1.2rem;
        }

        .footer-section p,
        .footer-section a {
            color: rgba(255,255,255,0.7);
            text-decoration: none;
            line-height: 2;
            transition: var(--transition);
        }

        .footer-section a:hover {
            color: var(--secondary);
        }

        .footer-bottom {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid rgba(255,255,255,0.1);
            color: rgba(255,255,255,0.5);
        }

        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .mobile-menu {
                display: flex;
            }

            .about-grid,
            .contact-container {
                grid-template-columns: 1fr;
            }

            .features {
                grid-template-columns: 1fr;
            }

            .cta-buttons {
                flex-direction: column;
                align-items: center;
            }

            .contact-form {
                padding: 30px;
            }
        }

        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.8s ease, transform 0.8s ease;
        }

        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body>
    <nav id="navbar">
        <a href="#" class="logo">PZ Furniture</a>
        <ul class="nav-links">
            <li><a href="#home">Home</a></li>
            <li><a href="#about">About</a></li>
            <li><a href="#products">Products</a></li>
            <li><a href="#services">Services</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
        <div class="mobile-menu">
            <span></span>
            <span></span>
            <span></span>
        </div>
    </nav>

    <section class="hero" id="home">
        <div class="hero-content">
            <h1>Crafting <span>Timeless</span> Elegance for Your Space</h1>
            <p>Premium furniture and interior design solutions in Warri, Delta State. Where luxury meets functionality.</p>
            <div class="cta-buttons">
                <a href="#products" class="btn btn-primary">View Collection</a>
                <a href="#contact" class="btn btn-secondary">Get Quote</a>
            </div>
        </div>
    </section>

    <section class="about" id="about">
        <div class="about-grid">
            <div class="about-image">
                <div class="about-image-placeholder">
                    [Your Workshop/Showroom Image]
                </div>
            </div>
            <div class="about-content">
                <h3>Excellence in Furniture Making Since Day One</h3>
                <p>Located at 88 Effurun Sapele Road, Warri, Delta State, PZ Furniture has established itself as a premier destination for high-quality furniture and interior design services in Nigeria.</p>
                <p>We blend modern minimalist aesthetics with luxury craftsmanship to create pieces that transform houses into homes. From custom sofas to complete interior makeovers, our team delivers excellence at every step.</p>
                
                <div class="features">
                    <div class="feature">
                        <div class="feature-icon">✓</div>
                        <span>Premium Materials</span>
                    </div>
                    <div class="feature">
                        <div class="feature-icon">✓</div>
                        <span>Custom Designs</span>
                    </div>
                    <div class="feature">
                        <div class="feature-icon">✓</div>
                        <span>Expert Craftsmen</span>
                    </div>
                    <div class="feature">
                        <div class="feature-icon">✓</div>
                        <span>Delivery & Installation</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section class="products" id="products">
        <div class="section-header">
            <h2>Our Collection</h2>
            <p>Discover our range of meticulously crafted furniture pieces designed to elevate your living and working spaces.</p>
        </div>

        <div class="product-categories">
            <button class="category-btn active">All</button>
            <button class="category-btn">Sofas</button>
            <button class="category-btn">Dining Sets</button>
            <button class="category-btn">Office</button>
            <button class="category-btn">Cabinets</button>
        </div>

        <div class="products-grid">
            <div class="product-card">
                <div class="product-image">
                    <div class="product-overlay">
                        <h3>Luxury Sectional Sofa</h3>
                        <p>Modern comfort meets classic elegance</p>
                    </div>
                </div>
                <div class="product-info">
                    <h3>Executive Sectional</h3>
                    <p>Italian Leather Finish</p>
                    <div class="price">₦850,000</div>
                </div>
            </div>

            <div class="product-card">
                <div class="product-image">
