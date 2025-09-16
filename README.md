<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dheeraj Tembhurne - Research Scientist</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
            line-height: 1.6;
            overflow-x: hidden;
            background: linear-gradient(135deg, #1e3c72 0%, #2a5298 100%);
            min-height: 100vh;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(20px);
            border-bottom: 1px solid rgba(255, 255, 255, 0.2);
            z-index: 1000;
            transition: all 0.3s ease;
        }

        .nav-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 2rem;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            color: white;
            text-decoration: none;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .nav-menu {
            display: flex;
            gap: 2rem;
            list-style: none;
        }

        .nav-menu a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
            position: relative;
            padding: 0.5rem 1rem;
            border-radius: 20px;
        }

        .nav-menu a:hover {
            color: #4ecdc4;
            background: rgba(255, 255, 255, 0.1);
            transform: translateY(-2px);
        }

        .nav-menu a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 50%;
            transform: translateX(-50%);
            width: 0;
            height: 2px;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            transition: width 0.3s ease;
        }

        .nav-menu a:hover::after {
            width: 80%;
        }

        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            position: relative;
            overflow: hidden;
        }

        .hero-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
            color: white;
            z-index: 2;
        }

        .hero-text h1 {
            font-size: clamp(2.5rem, 6vw, 4rem);
            font-weight: 700;
            margin-bottom: 1rem;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4, #45b7d1);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: fadeInUp 1s ease-out;
        }

        .hero-text .subtitle {
            font-size: 1.5rem;
            color: #4ecdc4;
            margin-bottom: 1rem;
            animation: fadeInUp 1s ease-out 0.2s both;
        }

        .hero-text p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            opacity: 0.9;
            animation: fadeInUp 1s ease-out 0.4s both;
        }

        .cta-buttons {
            display: flex;
            gap: 1rem;
            animation: fadeInUp 1s ease-out 0.6s both;
        }

        .cta-button {
            display: inline-block;
            padding: 1rem 2rem;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            transition: all 0.3s ease;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
        }

        .cta-primary {
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            color: white;
        }

        .cta-secondary {
            background: rgba(255, 255, 255, 0.1);
            color: white;
            border: 2px solid rgba(255, 255, 255, 0.3);
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.4);
        }

        .hero-image {
            display: flex;
            justify-content: center;
            align-items: center;
            animation: fadeInUp 1s ease-out 0.8s both;
        }

        .profile-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(20px);
            border-radius: 30px;
            padding: 2rem;
            text-align: center;
            border: 1px solid rgba(255, 255, 255, 0.2);
            transition: all 0.3s ease;
        }

        .profile-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
        }

        .profile-img {
            width: 200px;
            height: 200px;
            border-radius: 50%;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            margin: 0 auto 1rem;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
            color: white;
        }

        /* Sections */
        .section {
            padding: 5rem 0;
            min-height: 100vh;
            display: none;
        }

        .section.active {
            display: block;
        }

        .section-title {
            text-align: center;
            color: white;
            font-size: 2.5rem;
            font-weight: 700;
            margin-bottom: 3rem;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        /* Science Section */
        .science-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
        }

        .research-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(20px);
            border-radius: 20px;
            padding: 2rem;
            border: 1px solid rgba(255, 255, 255, 0.2);
            transition: all 0.3s ease;
            color: white;
        }

        .research-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
        }

        .research-icon {
            width: 60px;
            height: 60px;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            margin-bottom: 1rem;
        }

        .research-card h3 {
            font-size: 1.3rem;
            margin-bottom: 1rem;
            color: #4ecdc4;
        }

        .research-card p {
            color: rgba(255, 255, 255, 0.8);
            line-height: 1.6;
        }

        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
            gap: 2rem;
        }

        .project-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(20px);
            border-radius: 20px;
            overflow: hidden;
            border: 1px solid rgba(255, 255, 255, 0.2);
            transition: all 0.3s ease;
        }

        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
        }

        .project-image {
            height: 200px;
            background: linear-gradient(45deg, #667eea, #764ba2);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3rem;
            color: white;
        }

        .project-content {
            padding: 2rem;
            color: white;
        }

        .project-content h3 {
            font-size: 1.3rem;
            margin-bottom: 1rem;
            color: #4ecdc4;
        }

        .project-content p {
            color: rgba(255, 255, 255, 0.8);
            margin-bottom: 1.5rem;
        }

        .project-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-bottom: 1rem;
        }

        .tag {
            background: rgba(255, 255, 255, 0.2);
            padding: 0.3rem 0.8rem;
            border-radius: 15px;
            font-size: 0.8rem;
            color: white;
        }

        .project-link {
            display: inline-block;
            color: #4ecdc4;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
        }

        .project-link:hover {
            color: #ff6b6b;
            transform: translateX(5px);
        }

        /* Images Section */
        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .gallery-item {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(20px);
            border-radius: 20px;
            overflow: hidden;
            border: 1px solid rgba(255, 255, 255, 0.2);
            transition: all 0.3s ease;
        }

        .gallery-item:hover {
            transform: scale(1.05);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
        }

        .gallery-image {
            height: 250px;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3rem;
            color: white;
        }

        .gallery-caption {
            padding: 1.5rem;
            color: white;
        }

        .gallery-caption h3 {
            font-size: 1.1rem;
            margin-bottom: 0.5rem;
            color: #4ecdc4;
        }

        .gallery-caption p {
            color: rgba(255, 255, 255, 0.8);
            font-size: 0.9rem;
        }

        /* Floating Elements */
        .floating-element {
            position: absolute;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            animation: float 6s ease-in-out infinite;
        }

        .floating-element:nth-child(1) {
            width: 100px;
            height: 100px;
            top: 20%;
            left: 10%;
            animation-delay: 0s;
        }

        .floating-element:nth-child(2) {
            width: 150px;
            height: 150px;
            top: 60%;
            right: 15%;
            animation-delay: 2s;
        }

        .floating-element:nth-child(3) {
            width: 80px;
            height: 80px;
            bottom: 20%;
            left: 20%;
            animation-delay: 4s;
        }

        /* Animations */
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

        @keyframes float {
            0%, 100% {
                transform: translateY(0px);
            }
            50% {
                transform: translateY(-20px);
            }
        }

        /* Mobile Menu Toggle */
        .mobile-menu-toggle {
            display: none;
            background: none;
            border: none;
            color: white;
            font-size: 1.5rem;
            cursor: pointer;
            padding: 0.5rem;
            transition: all 0.3s ease;
        }

        .mobile-menu-toggle:hover {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 5px;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .mobile-menu-toggle {
                display: block;
            }

            .nav-menu {
                flex-direction: column;
                position: absolute;
                top: 100%;
                left: 0;
                width: 100%;
                background: rgba(30, 60, 114, 0.95);
                backdrop-filter: blur(20px);
                padding: 1.5rem;
                display: none;
                border-top: 1px solid rgba(255, 255, 255, 0.3);
                box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
                opacity: 0;
                transform: translateY(-10px);
                transition: all 0.3s ease;
                z-index: 1000;
            }

            .nav-menu.active {
                display: flex !important;
                opacity: 1;
                transform: translateY(0);
            }

            .nav-menu li {
                margin: 0.5rem 0;
            }

            .nav-menu a {
                padding: 1rem 1.5rem;
                text-align: center;
                border-radius: 10px;
                display: block;
                color: white !important;
                font-weight: 600;
                font-size: 1.1rem;
                background: rgba(255, 255, 255, 0.1);
                border: 1px solid rgba(255, 255, 255, 0.2);
                transition: all 0.3s ease;
            }

            .nav-menu a:hover {
                background: rgba(255, 255, 255, 0.2);
                color: #4ecdc4 !important;
                transform: translateY(-2px);
                box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
            }
            
            .hero-content {
                grid-template-columns: 1fr;
                text-align: center;
                gap: 2rem;
            }

            .hero-text h1 {
                font-size: 2.5rem;
            }

            .hero-text .subtitle {
                font-size: 1.2rem;
            }

            .cta-buttons {
                flex-direction: column;
                align-items: center;
                gap: 1rem;
            }

            .cta-button {
                width: 100%;
                max-width: 250px;
                text-align: center;
            }

            .profile-card {
                padding: 1.5rem;
            }

            .profile-img {
                width: 150px;
                height: 150px;
                font-size: 3rem;
            }
            
            .science-grid,
            .projects-grid,
            .gallery-grid {
                grid-template-columns: 1fr;
            }

            .research-card,
            .project-card,
            .gallery-item {
                margin-bottom: 1rem;
            }

            .section-title {
                font-size: 2rem;
            }

            .container {
                padding: 0 15px;
            }
            
            .floating-element {
                display: none;
            }

            /* Mobile-specific improvements */
            .project-content {
                padding: 1.5rem;
            }

            .project-tags {
                justify-content: center;
            }

            .gallery-image {
                height: 200px;
                font-size: 2.5rem;
            }
        }

        @media (max-width: 480px) {
            .hero-text h1 {
                font-size: 2rem;
            }

            .hero-text .subtitle {
                font-size: 1rem;
            }

            .hero-text p {
                font-size: 1rem;
            }

            .section-title {
                font-size: 1.8rem;
            }

            .research-card,
            .project-card {
                padding: 1.5rem;
            }

            .profile-img {
                width: 120px;
                height: 120px;
                font-size: 2.5rem;
            }

            .nav-container {
                padding: 1rem;
            }

            .logo {
                font-size: 1.5rem;
            }
        }
    </style>
</head>
<body>
    <nav>
        <div class="nav-container">
            <a href="#" class="logo">DHEERAJ TEMBHURNE</a>
            <button class="mobile-menu-toggle" onclick="toggleMobileMenu()">☰</button>
            <ul class="nav-menu" id="navMenu">
                <li><a href="#home" onclick="showSection('home'); closeMobileMenu()">Home</a></li>
                <li><a href="#science" onclick="showSection('science'); closeMobileMenu()">Science</a></li>
                <li><a href="#projects" onclick="showSection('projects'); closeMobileMenu()">Projects</a></li>
                <li><a href="#images" onclick="showSection('images'); closeMobileMenu()">Images</a></li>
            </ul>
        </div>
    </nav>

    <!-- Home Section -->
    <section class="hero active" id="home">
        
        
        <div class="container">
            <div class="hero-content">
                <div class="hero-text">
                    <h1>Dheeraj Tembhurne</h1>
                    <div class="subtitle">Computational Physicist, Content Creator and Teacher</div>
                    <p>Exploring the frontiers of quantum computing and machine learning to solve complex problems in materials science and beyond.</p>
                    <div class="cta-buttons">
                        <a href="#science" class="cta-button cta-primary" onclick="showSection('science')">View Research</a>
                        <a href="#projects" class="cta-button cta-secondary" onclick="showSection('projects')">See Projects</a>
                    </div>
                </div>
                <div class="hero-image">
                    <div class="profile-card">
                        <div class="profile-img">🧬</div>
                        <h3>MS in Physics</h3>
                        <p>IISER PUNE • 2022</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Science Section -->
    <section class="section" id="science">
        <div class="container">
            <h2 class="section-title">Research & Science</h2>
            <div class="science-grid">
                <div class="research-card">
                    <div class="research-icon">⚛️</div>
                    <h3>Quantum Computing</h3>
                    <p>Developing novel quantum algorithms for optimization problems in materials science. Focus on variational quantum eigensolvers and quantum machine learning applications.</p>
                </div>
                
                <div class="research-card">
                    <div class="research-icon">🔬</div>
                    <h3>Materials Science</h3>
                    <p>Computational modeling of 2D materials and their electronic properties. Published 15+ papers on graphene-based nanostructures and their applications in electronics.</p>
                </div>
                
                <div class="research-card">
                    <div class="research-icon">🧠</div>
                    <h3>Machine Learning</h3>
                    <p>Applying deep learning techniques to predict material properties and accelerate discovery of new compounds. Specialized in neural network architectures for scientific computing.</p>
                </div>
                
                <div class="research-card">
                    <div class="research-icon">📊</div>
                    <h3>Data Science</h3>
                    <p>Large-scale analysis of experimental data using advanced statistical methods. Expertise in uncertainty quantification and Bayesian inference for scientific applications.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section class="section" id="projects">
        <div class="container">
            <h2 class="section-title">Projects</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <div class="project-image">🔬</div>
                    <div class="project-content">
                        <h3>QuantumMat Simulator</h3>
                        <p>Open-source quantum simulator for materials science applications. Enables researchers to model quantum effects in solid-state systems.</p>
                        <div class="project-tags">
                            <span class="tag">Python</span>
                            <span class="tag">Quantum Computing</span>
                            <span class="tag">Open Source</span>
                        </div>
                        <a href="#" class="project-link">View on GitHub →</a>
                    </div>
                </div>
                
                <div class="project-card">
                    <div class="project-image">🧬</div>
                    <div class="project-content">
                        <h3>Neural Materials Discovery</h3>
                        <p>Machine learning pipeline for predicting material properties from crystal structure. Achieved 95% accuracy in predicting band gaps.</p>
                        <div class="project-tags">
                            <span class="tag">TensorFlow</span>
                            <span class="tag">Materials Science</span>
                            <span class="tag">Deep Learning</span>
                        </div>
                        <a href="#" class="project-link">Learn More →</a>
                    </div>
                </div>
                
                <div class="project-card">
                    <div class="project-image">📊</div>
                    <div class="project-content">
                        <h3>LabData Analytics</h3>
                        <p>Interactive dashboard for analyzing experimental data from multiple research groups. Real-time visualization and statistical analysis tools.</p>
                        <div class="project-tags">
                            <span class="tag">React</span>
                            <span class="tag">D3.js</span>
                            <span class="tag">Data Visualization</span>
                        </div>
                        <a href="#" class="project-link">View Demo →</a>
                    </div>
                </div>
                
                <div class="project-card">
                    <div class="project-image">⚡</div>
                    <div class="project-content">
                        <h3>Quantum Error Correction</h3>
                        <p>Implementation of surface code error correction for quantum computers. Focuses on improving fidelity of quantum computations.</p>
                        <div class="project-tags">
                            <span class="tag">Qiskit</span>
                            <span class="tag">Quantum Computing</span>
                            <span class="tag">Error Correction</span>
                        </div>
                        <a href="#" class="project-link">Research Paper →</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Images Section -->
    <section class="section" id="images">
        <div class="container">
            <h2 class="section-title">Images & Visualizations</h2>
            <div class="gallery-grid">
                <div class="gallery-item">
                    <div class="gallery-image">📸</div>
                    <div class="gallery-caption">
                        <h3>Quantum Circuit Visualization</h3>
                        <p>3D visualization of quantum circuits used in materials simulation</p>
                    </div>
                </div>
                
                <div class="gallery-item">
                    <div class="gallery-image">🔬</div>
                    <div class="gallery-caption">
                        <h3>Lab Equipment</h3>
                        <p>State-of-the-art quantum computing lab at MIT</p>
                    </div>
                </div>
                
                <div class="gallery-item">
                    <div class="gallery-image">📊</div>
                    <div class="gallery-caption">
                        <h3>Data Analysis Results</h3>
                        <p>Machine learning predictions vs experimental results</p>
                    </div>
                </div>
                
                <div class="gallery-item">
                    <div class="gallery-image">🧬</div>
                    <div class="gallery-caption">
                        <h3>Crystal Structure</h3>
                        <p>3D model of novel 2D material discovered through ML</p>
                    </div>
                </div>
                
                <div class="gallery-item">
                    <div class="gallery-image">⚛️</div>
                    <div class="gallery-caption">
                        <h3>Quantum Simulation</h3>
                        <p>Electron density visualization in quantum materials</p>
                    </div>
                </div>
                
                <div class="gallery-item">
                    <div class="gallery-image">🌟</div>
                    <div class="gallery-caption">
                        <h3>Conference Presentation</h3>
                        <p>Speaking at the International Quantum Computing Conference</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <script>
        function toggleMobileMenu() {
            const navMenu = document.getElementById('navMenu');
            const toggle = document.querySelector('.mobile-menu-toggle');
            
            if (navMenu.classList.contains('active')) {
                navMenu.classList.remove('active');
                toggle.innerHTML = '☰';
            } else {
                navMenu.classList.add('active');
                toggle.innerHTML = '✕';
            }
        }

        function closeMobileMenu() {
            const navMenu = document.getElementById('navMenu');
            const toggle = document.querySelector('.mobile-menu-toggle');
            navMenu.classList.remove('active');
            toggle.innerHTML = '☰';
        }

        function showSection(sectionId) {
            // Hide all sections
            const sections = document.querySelectorAll('.section, .hero');
            sections.forEach(section => {
                section.classList.remove('active');
            });
            
            // Show selected section
            if (sectionId === 'home') {
                document.getElementById('home').classList.add('active');
            } else {
                document.getElementById(sectionId).classList.add('active');
            }
        }

        // Close mobile menu when clicking outside
        document.addEventListener('click', function(event) {
            const navMenu = document.getElementById('navMenu');
            const toggle = document.querySelector('.mobile-menu-toggle');
            const nav = document.querySelector('nav');
            
            if (!nav.contains(event.target) && navMenu.classList.contains('active')) {
                navMenu.classList.remove('active');
                toggle.innerHTML = '☰';
            }
        });

        // Navbar background on scroll
        window.addEventListener('scroll', () => {
            const nav = document.querySelector('nav');
            if (window.scrollY > 100) {
                nav.style.background = 'rgba(255, 255, 255, 0.15)';
            } else {
                nav.style.background = 'rgba(255, 255, 255, 0.1)';
            }
        });

        // Parallax effect for floating elements
        window.addEventListener('scroll', () => {
            const scrolled = window.pageYOffset;
            const parallaxElements = document.querySelectorAll('.floating-element');
            
            parallaxElements.forEach((element, index) => {
                const speed = 0.5 + (index * 0.2);
                element.style.transform = `translateY(${scrolled * speed}px)`;
            });
        });
    </script>
</body>
</html>
