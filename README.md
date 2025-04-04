# manhway.github.io  <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ManhwaHub - Premium Manhwa Reading Experience</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* Base Styles */
        :root {
            --primary: #ff6600;
            --primary-dark: #e65c00;
            --dark: #0a0a0a;
            --dark-light: #1a1a1a;
            --darker: #2a2a2a;
            --light: #e0e0e0;
            --gray: #aaa;
            --darker-gray: #666;
        }
        
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }
        
        body {
            font-family: 'Poppins', 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: var(--dark-light);
            color: var(--light);
            line-height: 1.6;
            overflow-x: hidden;
        }
        
        /* Navigation */
        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            background-color: var(--dark);
            padding: 1rem 2rem;
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 15px rgba(0, 0, 0, 0.5);
            transition: all 0.3s ease;
        }
        
        .navbar.scrolled {
            padding: 0.5rem 2rem;
            background-color: rgba(10, 10, 10, 0.95);
            backdrop-filter: blur(10px);
        }
        
        .logo {
            font-size: 2rem;
            font-weight: bold;
            color: var(--primary);
            text-decoration: none;
            font-family: 'Bangers', 'Arial Black', sans-serif;
            letter-spacing: 1px;
            text-shadow: 0 2px 5px rgba(255, 102, 0, 0.3);
        }
        
        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }
        
        .nav-links a {
            color: var(--light);
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s;
            position: relative;
            padding: 0.5rem 0;
        }
        
        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background-color: var(--primary);
            transition: width 0.3s;
        }
        
        .nav-links a:hover::after {
            width: 100%;
        }
        
        .nav-links a:hover {
            color: var(--primary);
        }
        
        .search-bar {
            display: flex;
            align-items: center;
            position: relative;
        }
        
        .search-bar input {
            padding: 0.7rem 1.2rem;
            border: none;
            border-radius: 25px 0 0 25px;
            width: 250px;
            background-color: var(--darker);
            color: white;
            font-family: inherit;
            transition: all 0.3s;
        }
        
        .search-bar input:focus {
            outline: none;
            box-shadow: 0 0 0 2px var(--primary);
        }
        
        .search-bar button {
            padding: 0.7rem 1.2rem;
            background-color: var(--primary);
            color: white;
            border: none;
            border-radius: 0 25px 25px 0;
            cursor: pointer;
            transition: all 0.3s;
        }
        
        .search-bar button:hover {
            background-color: var(--primary-dark);
        }
        
        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)), 
                        url('https://i.imgur.com/8QZQZQZ.jpg');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            height: 80vh;
            min-height: 500px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 0 2rem;
            position: relative;
            overflow: hidden;
        }
        
        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at center, transparent 0%, rgba(0,0,0,0.8) 100%);
            z-index: 1;
        }
        
        .hero-content {
            position: relative;
            z-index: 2;
            max-width: 800px;
        }
        
        .hero h1 {
            font-size: 4rem;
            margin-bottom: 1.5rem;
            color: var(--primary);
            text-shadow: 0 2px 10px rgba(0, 0, 0, 0.5);
            animation: fadeInUp 1s ease;
        }
        
        .hero p {
            font-size: 1.3rem;
            margin-bottom: 2.5rem;
            animation: fadeInUp 1s ease 0.2s forwards;
            opacity: 0;
        }
        
        .cta-button {
            padding: 1rem 2.5rem;
            background-color: var(--primary);
            color: white;
            border: none;
            border-radius: 30px;
            font-size: 1.1rem;
            cursor: pointer;
            transition: all 0.3s;
            text-decoration: none;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
            animation: fadeInUp 1s ease 0.4s forwards;
            opacity: 0;
            box-shadow: 0 5px 15px rgba(255, 102, 0, 0.3);
        }
        
        .cta-button:hover {
            background-color: var(--primary-dark);
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(255, 102, 0, 0.4);
        }
        
        /* Featured Manhwa */
        .featured {
            padding: 5rem 2rem;
            position: relative;
        }
        
        .section-title {
            font-size: 2.5rem;
            margin-bottom: 3rem;
            color: var(--primary);
            position: relative;
            display: inline-block;
            text-align: center;
            width: 100%;
        }
        
        .section-title::after {
            content: '';
            position: absolute;
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 4px;
            background-color: var(--primary);
            border-radius: 2px;
        }
        
        .manhwa-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
            gap: 2.5rem;
            margin-top: 3rem;
        }
        
        .manhwa-card {
            background-color: var(--darker);
            border-radius: 10px;
            overflow: hidden;
            transition: all 0.3s ease;
            cursor: pointer;
            position: relative;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }
        
        .manhwa-card:hover {
            transform: translateY(-10px) scale(1.03);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.3);
        }
        
        .manhwa-cover {
            width: 100%;
            height: 320px;
            object-fit: cover;
            transition: transform 0.5s ease;
        }
        
        .manhwa-card:hover .manhwa-cover {
            transform: scale(1.05);
        }
        
        .manhwa-info {
            padding: 1.5rem;
        }
        
        .manhwa-info h3 {
            margin-bottom: 0.5rem;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
            font-size: 1.1rem;
        }
        
        .manhwa-meta {
            display: flex;
            justify-content: space-between;
            color: var(--gray);
            font-size: 0.9rem;
            margin-top: 0.5rem;
        }
        
        .manhwa-status {
            padding: 0.2rem 0.5rem;
            border-radius: 3px;
            font-size: 0.7rem;
            font-weight: bold;
            text-transform: uppercase;
        }
        
        .status-ongoing {
            background-color: rgba(0, 200, 0, 0.2);
            color: #00c800;
        }
        
        .status-completed {
            background-color: rgba(0, 150, 255, 0.2);
            color: #0096ff;
        }
        
        .status-hiatus {
            background-color: rgba(255, 150, 0, 0.2);
            color: #ff9600;
        }
        
        .badge {
            position: absolute;
            top: 15px;
            right: 15px;
            background-color: var(--primary);
            color: white;
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: bold;
            z-index: 2;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
        }
        
        .bookmark-btn {
            position: absolute;
            top: 15px;
            left: 15px;
            background-color: rgba(0, 0, 0, 0.7);
            color: white;
            border: none;
            border-radius: 50%;
            width: 35px;
            height: 35px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 2;
            transition: all 0.3s;
        }
        
        .bookmark-btn:hover {
            background-color: var(--primary);
            transform: scale(1.1);
        }
        
        .bookmark-btn.bookmarked {
            color: var(--primary);
        }
        
        /* Chapter List Modal */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.9);
            z-index: 1000;
            overflow-y: auto;
            opacity: 0;
            transition: opacity 0.3s;
        }
        
        .modal.show {
            opacity: 1;
        }
        
        .modal-content {
            background-color: var(--darker);
            margin: 3rem auto;
            padding: 2.5rem;
            border-radius: 10px;
            width: 85%;
            max-width: 1000px;
            position: relative;
            transform: translateY(20px);
            transition: transform 0.3s;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
        }
        
        .modal.show .modal-content {
            transform: translateY(0);
        }
        
        .close-modal {
            position: absolute;
            top: 1.5rem;
            right: 1.5rem;
            font-size: 1.8rem;
            color: var(--gray);
            cursor: pointer;
            transition: all 0.3s;
            background: none;
            border: none;
        }
        
        .close-modal:hover {
            color: var(--primary);
            transform: rotate(90deg);
        }
        
        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 2rem;
        }
        
        .modal-title {
            font-size: 1.8rem;
            color: var(--primary);
        }
        
        .chapters-list {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
            gap: 1.2rem;
        }
        
        .chapter-item {
            background-color: var(--dark-light);
            padding: 1rem;
            border-radius: 8px;
            text-align: center;
            transition: all 0.3s;
            position: relative;
            overflow: hidden;
        }
        
        .chapter-item::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(255,102,0,0.1) 0%, rgba(255,102,0,0) 100%);
            opacity: 0;
            transition: opacity 0.3s;
        }
        
        .chapter-item:hover::before {
            opacity: 1;
        }
        
        .chapter-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }
        
        .chapter-item a {
            color: white;
            text-decoration: none;
            display: block;
            font-weight: 500;
        }
        
        .chapter-date {
            display: block;
            font-size: 0.8rem;
            color: var(--gray);
            margin-top: 0.5rem;
        }
        
        /* Chapter Reader */
        .reader-container {
            padding: 3rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
            display: none;
            opacity: 0;
            transition: opacity 0.5s;
        }
        
        .reader-container.show {
            display: block;
            opacity: 1;
        }
        
        .reader-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 2rem;
            background-color: var(--darker);
            padding: 1rem 1.5rem;
            border-radius: 8px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }
        
        .chapter-title {
            font-size: 1.5rem;
            color: var(--primary);
        }
        
        .chapter-nav {
            display: flex;
            gap: 1rem;
        }
        
        .chapter-nav button {
            padding: 0.7rem 1.5rem;
            background-color: var(--primary);
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: all 0.3s;
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }
        
        .chapter-nav button:hover {
            background-color: var(--primary-dark);
            transform: translateY(-2px);
        }
        
        .chapter-nav button:disabled {
            background-color: var(--darker-gray);
            cursor: not-allowed;
            transform: none;
        }
        
        .reader-content {
            background-color: var(--darker);
            padding: 2rem;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }
        
        .reader-page {
            margin-bottom: 2rem;
            text-align: center;
        }
        
        .reader-page img {
            max-width: 100%;
            border-radius: 5px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
            transition: transform 0.3s;
        }
        
        .reader-page img:hover {
            transform: scale(1.01);
        }
        
        .page-controls {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 2rem;
            margin-top: 2rem;
            background-color: var(--dark-light);
            padding: 1rem;
            border-radius: 8px;
        }
        
        .page-controls button {
            padding: 0.7rem 1.5rem;
            background-color: var(--primary);
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: all 0.3s;
            font-weight: 600;
        }
        
        .page-controls button:hover {
            background-color: var(--primary-dark);
            transform: translateY(-2px);
        }
        
        .page-controls button:disabled {
            background-color: var(--darker-gray);
            cursor: not-allowed;
            transform: none;
        }
        
        .page-indicator {
            font-weight: 600;
            color: var(--gray);
        }
        
        /* Footer */
        footer {
            background-color: var(--dark);
            padding: 4rem 2rem 2rem;
            text-align: center;
            margin-top: 5rem;
            position: relative;
        }
        
        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 3rem;
            text-align: left;
        }
        
        .footer-column h3 {
            color: var(--primary);
            margin-bottom: 1.5rem;
            font-size: 1.2rem;
        }
        
        .footer-links {
            list-style: none;
        }
        
        .footer-links li {
            margin-bottom: 0.8rem;
        }
        
        .footer-links a {
            color: var(--gray);
            text-decoration: none;
            transition: all 0.3s;
            display: inline-block;
        }
        
        .footer-links a:hover {
            color: var(--primary);
            transform: translateX(5px);
        }
        
        .social-links {
            display: flex;
            gap: 1rem;
            margin-top: 1.5rem;
        }
        
        .social-links a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background-color: var(--dark-light);
            border-radius: 50%;
            color: var(--light);
            transition: all 0.3s;
        }
        
        .social-links a:hover {
            background-color: var(--primary);
            transform: translateY(-5px);
        }
        
        .copyright {
            color: var(--darker-gray);
            font-size: 0.9rem;
            margin-top: 3rem;
            padding-top: 2rem;
            border-top: 1px solid var(--dark-light);
        }
        
        /* Scroll to Top Button */
        .to-top {
            position: fixed;
            bottom: 30px;
            right: 30px;
            background-color: var(--primary);
            color: white;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            opacity: 0;
            visibility: hidden;
            transition: all 0.3s;
            z-index: 999;
            box-shadow: 0 5px 15px rgba(255, 102, 0, 0.3);
        }
        
        .to-top.visible {
            opacity: 1;
            visibility: visible;
        }
        
        .to-top:hover {
            background-color: var(--primary-dark);
            transform: translateY(-5px);
        }
        
        /* Loading Spinner */
        .loading-spinner {
            display: none;
            width: 50px;
            height: 50px;
            margin: 3rem auto;
            border: 5px solid var(--dark-light);
            border-top: 5px solid var(--primary);
            border-radius: 50%;
            animation: spin 1s linear infinite;
        }
        
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        
        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        /* Responsive Design */
        @media (max-width: 1024px) {
            .hero h1 {
                font-size: 3rem;
            }
            
            .manhwa-grid {
                grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
            }
        }
        
        @media (max-width: 768px) {
            .navbar {
                flex-direction: column;
                gap: 1.5rem;
                padding: 1.5rem;
            }
            
            .nav-links {
                flex-wrap: wrap;
                justify-content: center;
                gap: 1rem;
            }
            
            .search-bar {
                width: 100%;
            }
            
            .search-bar input {
                width: 100%;
            }
            
            .hero {
                height: 70vh;
            }
            
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .hero p {
                font-size: 1.1rem;
            }
            
            .section-title {
                font-size: 2rem;
            }
            
            .modal-content {
                width: 95%;
                padding: 1.5rem;
            }
            
            .chapters-list {
                grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
            }
            
            .reader-header {
                flex-direction: column;
                gap: 1rem;
                text-align: center;
            }
            
            .page-controls {
                flex-direction: column;
                gap: 1rem;
            }
        }
        
        @media (max-width: 480px) {
            .hero h1 {
                font-size: 2rem;
            }
            
            .manhwa-grid {
                grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
                gap: 1.5rem;
            }
            
            .chapters-list {
                grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
                gap: 1rem;
            }
        }
    </style>
    <link href="https://fonts.googleapis.com/css2?family=Bangers&family=Poppins:wght@400;500;600;700&display=swap" rel="stylesheet">
</head>
<body>
    <!-- Navigation Bar -->
    <nav class="navbar" id="navbar">
        <a href="#" class="logo">MANHWAHUB</a>
        <ul class="nav-links">
            <li><a href="#"><i class="fas fa-home"></i> Home</a></li>
            <li><a href="#"><i class="fas fa-fire"></i> Popular</a></li>
            <li><a href="#"><i class="fas fa-tags"></i> Genres</a></li>
            <li><a href="#"><i class="fas fa-star"></i> New Releases</a></li>
            <li><a href="#"><i class="fas fa-bookmark"></i> Bookmarks</a></li>
        </ul>
        <div class="search-bar">
            <input type="text" placeholder="Search manhwa...">
            <button><i class="fas fa-search"></i></button>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <h1>Immerse Yourself in Korean Webcomics</h1>
            <p>Discover the best manhwa series with daily updates, high-quality scans, and a seamless reading experience.</p>
            <a href="#featured" class="cta-button">Start Reading Now</a>
        </div>
    </section>

    <!-- Featured Manhwa -->
    <section class="featured" id="featured">
        <h2 class="section-title">Popular Manhwa Series</h2>
        
        <div class="genre-filter">
            <button class="genre-btn active" data-genre="all">All Genres</button>
            <button class="genre-btn" data-genre="action"><i class="fas fa-fist-raised"></i> Action</button>
            <button class="genre-btn" data-genre="fantasy"><i class="fas fa-hat-wizard"></i> Fantasy</button>
            <button class="genre-btn" data-genre="romance"><i class="fas fa-heart"></i> Romance</button>
            <button class="genre-btn" data-genre="comedy"><i class="fas fa-laugh-squint"></i> Comedy</button>
            <button class="genre-btn" data-genre="drama"><i class="fas fa-theater-masks"></i> Drama</button>
        </div>
        
        <div class="manhwa-grid" id="manhwaGrid">
            <!-- Manhwa cards will be generated by JavaScript -->
        </div>
        <div class="loading-spinner" id="loadingSpinner"></div>
    </section>

    <!-- Chapter List Modal -->
    <div class="modal" id="chaptersModal">
        <div class="modal-content">
            <button class="close-modal">&times;</button>
            <div class="modal-header">
                <h2 class="modal-title" id="modal-title">Manhwa Chapters</h2>
                <div class="chapter-nav">
                    <button id="prev-chapter-modal"><i class="fas fa-arrow-left"></i> Prev</button>
                    <button id="next-chapter-modal">Next <i class="fas fa-arrow-right"></i></button>
                </div>
            </div>
            <div class="chapters-list" id="chaptersList">
                <!-- Chapters will be generated by JavaScript -->
            </div>
        </div>
    </div>

    <!-- Chapter Reader -->
    <section class="reader-container" id="reader">
        <div class="reader-header">
            <h3 class="chapter-title" id="chapter-title">Manhwa - Chapter 1</h3>
            <div class="chapter-nav">
                <button id="prev-chapter"><i class="fas fa-arrow-left"></i> Previous Chapter</button>
                <button id="next-chapter">Next Chapter <i class="fas fa-arrow-right"></i></button>
            </div>
        </div>
        <div class="reader-content" id="readerContent">
            <!-- Pages will be generated by JavaScript -->
        </div>
        <div class="page-controls">
            <button id="prev-page"><i class="fas fa-arrow-left"></i> Previous Page</button>
            <span class="page-indicator" id="page-indicator">Page 1 of 10</span>
            <button id="next-page">Next Page <i class="fas fa-arrow-right"></i></button>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <div class="footer-column">
                <h3>ManhwaHub</h3>
                <p>Your premier destination for high-quality Korean webcomics. Updated daily with the latest chapters.</p>
                <div class="social-links">
                    <a href="#"><i class="fab fa-facebook-f"></i></a>
                    <a href="#"><i class="fab fa-twitter"></i></a>
                    <a href="#"><i class="fab fa-instagram"></i></a>
                    <a href="#"><i class="fab fa-discord"></i></a>
                </div>
            </div>
            <div class="footer-column">
                <h3>Quick Links</h3>
                <ul class="footer-links">
                    <li><a href="#">Home</a></li>
                    <li><a href="#">Popular Manhwa</a></li>
                    <li><a href="#">New Releases</a></li>
                    <li><a href="#">Genres</a></li>
                    <li><a href="#">Bookmarks</a></li>
                </ul>
            </div>
            <div class="footer-column">
                <h3>Information</h3>
                <ul class="footer-links">
                    <li><a href="#">About Us</a></li>
                    <li><a href="#">Terms of Service</a></li>
                    <li><a href="#">Privacy Policy</a></li>
                    <li><a href="#">DMCA</a></li>
                    <li><a href="#">Contact</a></li>
                </ul>
            </div>
            <div class="footer-column">
                <h3>Support</h3>
                <ul class="footer-links">
                    <li><a href="#">FAQ</a></li>
                    <li><a href="#">Help Center</a></li>
                    <li><a href="#">Report Issue</a></li>
                    <li><a href="#">Suggestions</a></li>
                    <li><a href="#">Donate</a></li>
                </ul>
            </div>
        </div>
        <p class="copyright">© 2023 ManhwaHub. All rights reserved. All manhwa are property of their respective owners.</p>
    </footer>

    <!-- Scroll to Top Button -->
    <div class="to-top" id="toTopBtn">
        <i class="fas fa-arrow-up"></i>
    </div>

    <script>
        /***********************************************************************
        * NOTE: This uses placeholder images. For a real site, you would need to:
        * 1. Replace placeholder image URLs with actual manhwa covers
        * 2. Add more chapters and pages to each manhwa
        * 3. Implement backend storage for the data
        * 4. Ensure you have proper rights to distribute any content
        ***********************************************************************/

        document.addEventListener('DOMContentLoaded', function() {
            // Enhanced manhwa data with more chapters and details
            const manhwaData = [
                {
                    id: 1,
                    title: "Solo Leveling",
                    cover: "https://i.imgur.com/J5Z9Q0x.jpg",
                    description: "In a world where hunters, humans who possess magical abilities, must battle deadly monsters to protect the human race from certain annihilation, a notoriously weak hunter named Sung Jin-Woo finds himself in a seemingly endless struggle for survival.",
                    author: "Chugong",
                    artist: "Jang Sung-Rak (Dubu)",
                    latestChapter: "Chapter 200",
                    isNew: true,
                    genre: ["action", "fantasy", "adventure"],
                    status: "completed",
                    rating: 4.9,
                    chapters: generateChapters("Solo Leveling", 200, 5)
                },
                {
                    id: 2,
                    title: "Tower of God",
                    cover: "https://i.imgur.com/K8LQY2F.jpg",
                    description: "The story follows a boy named Twenty-Fifth Bam, who has spent most of his life trapped beneath a vast and mysterious Tower, as he climbs it with his friends, facing challenges at each floor.",
                    author: "SIU",
                    artist: "SIU",
                    latestChapter: "Chapter 550",
                    isNew: false,
                    genre: ["action", "fantasy", "adventure", "drama"],
                    status: "ongoing",
                    rating: 4.8,
                    chapters: generateChapters("Tower of God", 550, 10)
                },
                {
                    id: 3,
                    title: "The Beginning After The End",
                    cover: "https://i.imgur.com/M9LQZ3X.jpg",
                    description: "King Grey has unrivaled strength, wealth, and prestige in a world governed by martial ability. However, solitude lingers closely behind those with great power. Reincarnated into a new world filled with magic and monsters, he'll get a second chance at life.",
                    author: "TurtleMe",
                    artist: "Fuyuki23",
                    latestChapter: "Chapter 180",
                    isNew: true,
                    genre: ["action", "fantasy", "isekai"],
                    status: "ongoing",
                    rating: 4.7,
                    chapters: generateChapters("The Beginning After The End", 180, 7)
                },
                {
                    id: 4,
                    title: "Omniscient Reader's Viewpoint",
                    cover: "https://i.imgur.com/N9LQY4F.jpg",
                    description: "Kim Dokja is an average office worker whose sole interest is reading his favorite web novel 'Three Ways to Survive the Apocalypse.' When the novel suddenly becomes reality, he is the only person who knows how the world will end.",
                    author: "singNsong",
                    artist: "Sleepy-C",
                    latestChapter: "Chapter 120",
                    isNew: false,
                    genre: ["action", "fantasy", "adventure"],
                    status: "ongoing",
                    rating: 4.8,
                    chapters: generateChapters("Omniscient Reader's Viewpoint", 120, 6)
                },
                {
                    id: 5,
                    title: "Legend of the Northern Blade",
                    cover: "https://i.imgur.com/O9LQZ5X.jpg",
                    description: "In a world where the strong prey on the weak, the Northern Heavenly Sect was the lone wolf that stood against the tyrants of the Central Heavenly Alliance. After the sect's downfall, the young successor to the sect, Jin Mu-Won, must survive in a world that wants him dead.",
                    author: "Woo-Gak",
                    artist: "Hae-Min",
                    latestChapter: "Chapter 150",
                    isNew: true,
                    genre: ["action", "fantasy", "martial-arts"],
                    status: "ongoing",
                    rating: 4.6,
                    chapters: generateChapters("Legend of the Northern Blade", 150, 8)
                },
                {
                    id: 6,
                    title: "Return of the Mount Hua Sect",
                    cover: "https://i.imgur.com/P9LQY6F.jpg",
                    description: "Chung Myung, the 13th disciple of the Mount Hua Sect, one of the 3 Great Swordsmen, defeats the leader of the Demonic Cult that brought destruction to the world. After 100 years, he reincarnates and returns to the Mount Hua Sect.",
                    author: "Biga",
                    artist: "Jin Soo-Cheol",
                    latestChapter: "Chapter 100",
                    isNew: true,
                    genre: ["action", "fantasy", "martial-arts", "comedy"],
                    status: "ongoing",
                    rating: 4.5,
                    chapters: generateChapters("Return of the Mount Hua Sect", 100, 4)
                },
                {
                    id: 7,
                    title: "The Great Mage Returns After 4000 Years",
                    cover: "https://i.imgur.com/Q9LQZ7X.jpg",
                    description: "The Great Mage Lucas Traumen was betrayed and sealed away. After 4000 years, he wakes up in the body of a descendant, Frey Blake. Now, he must regain his former power and uncover the truth behind his betrayal.",
                    author: "Barnacle",
                    artist: "Wookjakga",
                    latestChapter: "Chapter 90",
                    isNew: true,
                    genre: ["action", "fantasy", "magic"],
                    status: "ongoing",
                    rating: 4.4,
                    chapters: generateChapters("The Great Mage Returns After 4000 Years", 90, 5)
                },
                {
                    id: 8,
                    title: "The Second Coming of Gluttony",
                    cover: "https://i.imgur.com/R9LQY8X.jpg",
                    description: "Seol Jihu was a gambling addict who lost everything—his family, his money, even his own life. After hitting rock bottom, he's given a second chance when he's transported to the world of Paradise.",
                    author: "Ro Yu-jin",
                    artist: "Wuxia",
                    latestChapter: "Chapter 80",
                    isNew: false,
                    genre: ["action", "fantasy", "adventure"],
                    status: "ongoing",
                    rating: 4.3,
                    chapters: generateChapters("The Second Coming of Gluttony", 80, 3)
                },
                {
                    id: 9,
                    title: "A Returner's Magic Should Be Special",
                    cover: "https://i.imgur.com/S9LQY9X.jpg",
                    description: "Desir Arman is the sole survivor of a party that was wiped out in the Shadow Labyrinth, one of the most dangerous dungeons in the world. When he wakes up, he finds himself 13 years in the past.",
                    author: "Usonan",
                    artist: "Wookjakga",
                    latestChapter: "Chapter 200",
                    isNew: false,
                    genre: ["action", "fantasy", "magic"],
                    status: "ongoing",
                    rating: 4.7,
                    chapters: generateChapters("A Returner's Magic Should Be Special", 200, 9)
                },
                {
                    id: 10,
                    title: "The Tutorial Is Too Hard",
                    cover: "https://i.imgur.com/T9LQY0X.jpg",
                    description: "One day, a mysterious message appears inviting people to challenge the Tutorial. Lee Ho-Jae chooses the hardest difficulty, Hell Mode, thinking it would be a simple game. He soon realizes it's anything but.",
                    author: "Gandara",
                    artist: "Kang Do-Han",
                    latestChapter: "Chapter 70",
                    isNew: true,
                    genre: ["action", "fantasy", "adventure"],
                    status: "ongoing",
                    rating: 4.2,
                    chapters: generateChapters("The Tutorial Is Too Hard", 70, 2)
                }
            ];

            // Function to generate chapters with realistic dates
            function generateChapters(title, totalChapters, pagesPerChapter) {
                const chapters = [];
                const now = new Date();
                
                for (let i = totalChapters; i >= 1; i--) {
                    const date = new Date(now);
                    date.setDate(date.getDate() - (totalChapters - i) * 7);
                    
                    const pages = [];
                    for (let j = 1; j <= pagesPerChapter; j++) {
                        pages.push(`https://i.imgur.com/${title.replace(/ /g, '').substring(0, 3).toUpperCase()}${i}P${j}.jpg`);
                    }
                    
                    chapters.push({
                        number: i,
                        title: `${title} - Chapter ${i}`,
                        pages: pages,
                        date: date.toISOString().split('T')[0]
                    });
                }
                
                return chapters;
            }

            // DOM Elements
            const manhwaGrid = document.getElementById('manhwaGrid');
            const loadingSpinner = document.getElementById('loadingSpinner');
            const genreBtns = document.querySelectorAll('.genre-btn');
            const chaptersModal = document.getElementById('chaptersModal');
            const modalTitle = document.getElementById('modal-title');
            const chaptersList = document.getElementById('chaptersList');
            const closeModal = document.querySelector('.close-modal');
            const prevChapterModalBtn = document.getElementById('prev-chapter-modal');
            const nextChapterModalBtn = document.getElementById('next-chapter-modal');
            const readerSection = document.getElementById('reader');
            const readerContent = document.getElementById('readerContent');
            const chapterTitle = document.getElementById('chapter-title');
            const prevChapterBtn = document.getElementById('prev-chapter');
            const nextChapterBtn = document.getElementById('next-chapter');
            const prevPageBtn = document.getElementById('prev-page');
            const nextPageBtn = document.getElementById('next-page');
            const pageIndicator = document.getElementById('page-indicator');
            const searchInput = document.querySelector('.search-bar input');
            const searchButton = document.querySelector('.search-bar button');
            const toTopBtn = document.getElementById('toTopBtn');
            const navbar = document.getElementById('navbar');

            // Current reading state
            let currentManhwa = null;
            let currentChapterIndex = 0;
            let currentPage = 1;
            let totalPages = 1;
            let bookmarkedManhwa = JSON.parse(localStorage.getItem('bookmarkedManhwa')) || [];

            // Generate manhwa cards
            function generateManhwaCards(filterGenre = 'all') {
                manhwaGrid.innerHTML = '';
                loadingSpinner.style.display = 'block';
                
                // Simulate loading delay
                setTimeout(() => {
                    const filteredManhwa = filterGenre === 'all' 
                        ? manhwaData 
                        : manhwaData.filter(manhwa => manhwa.genre.includes(filterGenre));
                    
                    filteredManhwa.forEach(manhwa => {
                        const isBookmarked = bookmarkedManhwa.includes(manhwa.id);
                        const card = document.createElement('div');
                        card.className = 'manhwa-card';
                        card.dataset.id = manhwa.id;
                        card.innerHTML = `
                            ${manhwa.isNew ? '<span class="badge">NEW</span>' : ''}
                            <button class="bookmark-btn ${isBookmarked ? 'bookmarked' : ''}" 
                                    data-id="${manhwa.id}">
                                <i class="fas fa-bookmark"></i>
                            </button>
                            <img src="${manhwa.cover}" alt="${manhwa.title}" class="manhwa-cover">
                            <div class="manhwa-info">
                                <h3>${manhwa.title}</h3>
                                <p>${manhwa.latestChapter}</p>
                                <div class="manhwa-meta">
                                    <span>⭐ ${manhwa.rating}</span>
                                    <span class="manhwa-status status-${manhwa.status}">${manhwa.status}</span>
                                </div>
                            </div>
                        `;
                        manhwaGrid.appendChild(card);
                        
                        // Add click event to each card
                        card.addEventListener('click', function(e) {
                            if (!e.target.classList.contains('bookmark-btn')) {
                                currentManhwa = manhwa;
                                showChaptersModal(manhwa);
                            }
                        });
                    });
                    
                    loadingSpinner.style.display = 'none';
                }, 800);
            }

            // Show chapters modal
            function showChaptersModal(manhwa) {
                modalTitle.textContent = `${manhwa.title} Chapters (${manhwa.chapters.length})`;
                chaptersList.innerHTML = '';
                
                manhwa.chapters.forEach((chapter, index) => {
                    const chapterItem = document.createElement('div');
                    chapterItem.className = 'chapter-item';
                    chapterItem.innerHTML = `
                        <a href="#" data-index="${index}">
                            Chapter ${chapter.number}
                            <span class="chapter-date">${chapter.date}</span>
                        </a>
                    `;
                    chaptersList.appendChild(chapterItem);
                    
                    // Add click event to chapter items
                    chapterItem.addEventListener('click', function(e) {
                        e.preventDefault();
                        loadChapter(manhwa, index);
                        closeChaptersModal();
                    });
                });
                
                // Update chapter nav buttons state
                updateChapterNavButtons();
                
                // Show modal with animation
                chaptersModal.classList.add('show');
                document.body.style.overflow = 'hidden';
            }

            // Close chapters modal
            function closeChaptersModal() {
                chaptersModal.classList.remove('show');
                document.body.style.overflow = '';
                
                // Delay for animation
                setTimeout(() => {
                    chaptersModal.style.display = 'none';
                }, 300);
            }

            // Load chapter
            function loadChapter(manhwa, chapterIndex) {
                const chapter = manhwa.chapters[chapterIndex];
                currentManhwa = manhwa;
                currentChapterIndex = chapterIndex;
                currentPage = 1;
                totalPages = chapter.pages.length;
                
                // Update UI
                chapterTitle.textContent = `${manhwa.title} - Chapter ${chapter.number}`;
                
                // Clear existing pages
                readerContent.innerHTML = '';
                
                // Add new pages
                chapter.pages.forEach((page, index) => {
                    const pageElement = document.createElement('div');
                    pageElement.className = 'reader-page';
                    pageElement.style.display = index === 0 ? 'block' : 'none';
                    pageElement.innerHTML = `
                        <img src="${page}" alt="Page ${index + 1}">
                    `;
                    readerContent.appendChild(pageElement);
                });
                
                // Update controls
                updatePageControls();
                updateChapterNavButtons();
                
                // Show reader
                readerSection.classList.add('show');
                
                // Scroll to reader
                setTimeout(() => {
                    readerSection.scrollIntoView({ behavior: 'smooth' });
                }, 100);
            }

            // Update page controls
            function updatePageControls() {
                pageIndicator.textContent = `Page ${currentPage} of ${totalPages}`;
                prevPageBtn.disabled = currentPage === 1;
                nextPageBtn.disabled = currentPage === totalPages;
                
                // Show only the current page
                const pages = document.querySelectorAll('.reader-page');
                pages.forEach((page, index) => {
                    page.style.display = index === currentPage - 1 ? 'block' : 'none';
                });
            }

            // Update chapter nav buttons state
            function updateChapterNavButtons() {
                if (!currentManhwa) return;
                
                prevChapterBtn.disabled = currentChapterIndex >= currentManhwa.chapters.length - 1;
                nextChapterBtn.disabled = currentChapterIndex <= 0;
                
                prevChapterModalBtn.disabled = currentChapterIndex >= currentManhwa.chapters.length - 1;
                nextChapterModalBtn.disabled = currentChapterIndex <= 0;
            }

            // Navigation events
            prevPageBtn.addEventListener('click', function() {
                if (currentPage > 1) {
                    currentPage--;
                    updatePageControls();
                }
            });
            
            nextPageBtn.addEventListener('click', function() {
                if (currentPage < totalPages) {
                    currentPage++;
                    updatePageControls();
                }
            });
            
            prevChapterBtn.addEventListener('click', function() {
                if (currentChapterIndex < currentManhwa.chapters.length - 1) {
                    currentChapterIndex++;
                    loadChapter(currentManhwa, currentChapterIndex);
                }
            });
            
            nextChapterBtn.addEventListener('click', function() {
                if (currentChapterIndex > 0) {
                    currentChapterIndex--;
                    loadChapter(currentManhwa, currentChapterIndex);
                }
            });
            
            prevChapterModalBtn.addEventListener('click', function() {
                if (currentChapterIndex < currentManhwa.chapters.length - 1) {
                    currentChapterIndex++;
                    loadChapter(currentManhwa, currentChapterIndex);
                }
            });
            
            nextChapterModalBtn.addEventListener('click', function() {
                if (currentChapterIndex > 0) {
                    currentChapterIndex--;
                    loadChapter(currentManhwa, currentChapterIndex);
                }
            });

            // Modal close event
            closeModal.addEventListener('click', closeChaptersModal);
            
            // Close modal when clicking outside
            chaptersModal.addEventListener('click', function(e) {
                if (e.target === chaptersModal) {
                    closeChaptersModal();
                }
            });

            // Bookmark functionality
            document.addEventListener('click', function(e) {
                if (e.target.closest('.bookmark-btn')) {
                    const btn = e.target.closest('.bookmark-btn');
                    const manhwaId = parseInt(btn.dataset.id);
                    const index = bookmarkedManhwa.indexOf(manhwaId);
                    
                    if (index === -1) {
                        bookmarkedManhwa.push(manhwaId);
                        btn.classList.add('bookmarked');
                    } else {
                        bookmarkedManhwa.splice(index, 1);
                        btn.classList.remove('bookmarked');
                    }
                    
                    localStorage.setItem('bookmarkedManhwa', JSON.stringify(bookmarkedManhwa));
                }
            });

            // Genre filter
            genreBtns.forEach(btn => {
                btn.addEventListener('click', () => {
                    genreBtns.forEach(b => b.classList.remove('active'));
                    btn.classList.add('active');
                    generateManhwaCards(btn.dataset.genre);
                });
            });

            // Search functionality
            searchButton.addEventListener('click', performSearch);
            
            // Allow search on Enter key
            searchInput.addEventListener('keypress', function(e) {
                if (e.key === 'Enter') {
                    performSearch();
                }
            });
            
            function performSearch() {
                const searchTerm = searchInput.value.trim().toLowerCase();
                if (searchTerm) {
                    const cards = document.querySelectorAll('.manhwa-card');
                    let hasResults = false;
                    
                    cards.forEach(card => {
                        const title = card.querySelector('h3').textContent.toLowerCase();
                        if (title.includes(searchTerm)) {
                            card.style.display = 'block';
                            hasResults = true;
                        } else {
                            card.style.display = 'none';
                        }
                    });
                    
                    if (!hasResults) {
                        manhwaGrid.innerHTML = `<div class="no-results">No manhwa found matching "${searchTerm}"</div>`;
                    }
                } else {
                    generateManhwaCards();
                }
            }

            // Scroll to top button
            window.addEventListener('scroll', () => {
                if (window.pageYOffset > 300) {
                    toTopBtn.classList.add('visible');
                } else {
                    toTopBtn.classList.remove('visible');
                }
                
                // Navbar effect
                if (window.pageYOffset > 100) {
                    navbar.classList.add('scrolled');
                } else {
                    navbar.classList.remove('scrolled');
                }
            });

            toTopBtn.addEventListener('click', () => {
                window.scrollTo({ top: 0, behavior: 'smooth' });
            });

            // Keyboard navigation
            document.addEventListener('keydown', function(e) {
                if (!readerSection.classList.contains('show')) return;
                
                switch(e.key) {
                    case 'ArrowLeft':
                        if (currentPage > 1) {
                            currentPage--;
                            updatePageControls();
                        } else if (currentChapterIndex > 0) {
                            currentChapterIndex--;
                            loadChapter(currentManhwa, currentChapterIndex);
                        }
                        break;
                    case 'ArrowRight':
                        if (currentPage < totalPages) {
                            currentPage++;
                            updatePageControls();
                        } else if (currentChapterIndex < currentManhwa.chapters.length - 1) {
                            currentChapterIndex++;
                            loadChapter(currentManhwa, currentChapterIndex);
                        }
                        break;
                }
            });

            // Initialize
            generateManhwaCards();
        });
    </script>
</body>
</html>
