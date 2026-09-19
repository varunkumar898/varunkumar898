<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Varun Kumar — Embedded Systems & Firmware Engineering</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Geist:wght@400;500;600;700&family=Geist+Mono:wght@400;500&display=swap');

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --bg: #0f0f0f;
            --surface: #1a1a1a;
            --surface-light: #2a2a2a;
            --border: #333333;
            --text: #f0f0f0;
            --text-secondary: #a0a0a0;
            --accent: #00d9ff;
            --accent-soft: #0099cc;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            background: var(--bg);
            color: var(--text);
            font-family: 'Geist', system-ui, -apple-system, sans-serif;
            line-height: 1.6;
            font-size: 16px;
        }

        *:focus-visible {
            outline: 2px solid var(--accent);
            outline-offset: 2px;
        }

        a {
            color: var(--accent);
            text-decoration: none;
            transition: color 0.3s;
        }

        a:hover {
            color: var(--accent-soft);
        }

        .container {
            max-width: 1100px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        section {
            padding: 5rem 0;
        }

        /* HERO */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: radial-gradient(circle at 20% 50%, rgba(0, 217, 255, 0.05) 0%, transparent 50%);
            pointer-events: none;
        }

        .hero-content {
            position: relative;
            z-index: 2;
            max-width: 800px;
        }

        .hero-badge {
            display: inline-block;
            padding: 0.5rem 1rem;
            background: rgba(0, 217, 255, 0.1);
            border: 1px solid rgba(0, 217, 255, 0.3);
            border-radius: 24px;
            font-size: 0.85rem;
            color: var(--accent);
            margin-bottom: 2rem;
            font-weight: 500;
            letter-spacing: 0.5px;
        }

        .hero h1 {
            font-size: clamp(2.5rem, 8vw, 4rem);
            font-weight: 700;
            line-height: 1.1;
            margin-bottom: 1.5rem;
            letter-spacing: -0.02em;
        }

        .hero h1 .highlight {
            color: var(--accent);
            background: linear-gradient(135deg, var(--accent) 0%, var(--accent-soft) 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .hero p {
            font-size: 1.1rem;
            color: var(--text-secondary);
            margin-bottom: 2rem;
            line-height: 1.8;
        }

        .cta-group {
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
            margin-top: 2rem;
        }

        .btn {
            padding: 0.875rem 1.75rem;
            border-radius: 8px;
            font-weight: 500;
            font-size: 1rem;
            border: 1px solid transparent;
            cursor: pointer;
            transition: all 0.3s ease;
            font-family: inherit;
        }

        .btn-primary {
            background: var(--accent);
            color: var(--bg);
        }

        .btn-primary:hover {
            background: var(--accent-soft);
            transform: translateY(-2px);
            box-shadow: 0 8px 24px rgba(0, 217, 255, 0.2);
        }

        .btn-secondary {
            border: 1px solid var(--border);
            color: var(--text);
            background: transparent;
        }

        .btn-secondary:hover {
            background: var(--surface-light);
            border-color: var(--accent);
            color: var(--accent);
        }

        /* ABOUT */
        .about {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
        }

        .about-text h2 {
            font-size: 2rem;
            margin-bottom: 1.5rem;
            font-weight: 700;
        }

        .about-text p {
            color: var(--text-secondary);
            margin-bottom: 1.5rem;
            line-height: 1.8;
        }

        .avatar-section {
            position: relative;
            height: 400px;
        }

        .avatar {
            width: 100%;
            height: 100%;
            border-radius: 16px;
            border: 1px solid var(--border);
            object-fit: cover;
            box-shadow: 0 20px 40px rgba(0, 217, 255, 0.1);
        }

        /* TECH STACK TABS */
        .tech-section h2 {
            font-size: 2rem;
            margin-bottom: 2rem;
            font-weight: 700;
            text-align: center;
        }

        .tabs {
            display: flex;
            gap: 0.5rem;
            border-bottom: 1px solid var(--border);
            margin-bottom: 2rem;
            overflow-x: auto;
            padding-bottom: 1rem;
        }

        .tab-btn {
            padding: 0.75rem 1.5rem;
            background: transparent;
            border: none;
            color: var(--text-secondary);
            cursor: pointer;
            font-size: 0.95rem;
            font-weight: 500;
            border-bottom: 2px solid transparent;
            transition: all 0.3s;
            white-space: nowrap;
        }

        .tab-btn.active {
            color: var(--accent);
            border-bottom-color: var(--accent);
        }

        .tab-btn:hover {
            color: var(--text);
        }

        .tab-content {
            display: none;
        }

        .tab-content.active {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 1.5rem;
        }

        .tech-card {
            background: var(--surface);
            padding: 1.5rem;
            border-radius: 12px;
            border: 1px solid var(--border);
            transition: all 0.3s;
            cursor: pointer;
        }

        .tech-card:hover {
            border-color: var(--accent);
            box-shadow: 0 8px 24px rgba(0, 217, 255, 0.1);
            transform: translateY(-2px);
        }

        .tech-emoji {
            font-size: 2rem;
            margin-bottom: 0.75rem;
        }

        .tech-name {
            font-size: 1.1rem;
            font-weight: 600;
            color: var(--text);
            margin-bottom: 0.5rem;
        }

        .tech-desc {
            color: var(--text-secondary);
            font-size: 0.95rem;
            line-height: 1.6;
        }

        /* FEATURED PROJECTS */
        .featured-header {
            text-align: center;
            margin-bottom: 3rem;
        }

        .featured-header h2 {
            font-size: 2rem;
            margin-bottom: 1rem;
            font-weight: 700;
        }

        .featured-header p {
            color: var(--text-secondary);
            font-size: 1.1rem;
        }

        .featured-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(330px, 1fr));
            gap: 2rem;
        }

        .project-card {
            background: var(--surface);
            border: 1px solid var(--border);
            border-radius: 12px;
            padding: 2rem;
            transition: all 0.3s ease;
            display: flex;
            flex-direction: column;
            position: relative;
            overflow: hidden;
            cursor: pointer;
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 3px;
            background: linear-gradient(90deg, var(--accent) 0%, var(--accent-soft) 100%);
            transform: scaleX(0);
            transform-origin: left;
            transition: transform 0.3s ease;
        }

        .project-card:hover {
            border-color: var(--accent);
            box-shadow: 0 12px 32px rgba(0, 217, 255, 0.1);
        }

        .project-card:hover::before {
            transform: scaleX(1);
        }

        .project-icon {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }

        .project-name {
            font-size: 1.2rem;
            font-weight: 600;
            margin-bottom: 0.75rem;
            color: var(--text);
        }

        .project-description {
            color: var(--text-secondary);
            font-size: 0.95rem;
            margin-bottom: 1.5rem;
            flex-grow: 1;
            line-height: 1.7;
        }

        .project-tags {
            display: flex;
            gap: 0.5rem;
            flex-wrap: wrap;
        }

        .tag {
            font-size: 0.8rem;
            padding: 0.3rem 0.8rem;
            background: rgba(0, 217, 255, 0.1);
            color: var(--accent);
            border-radius: 4px;
            font-family: 'Geist Mono', monospace;
        }

        .project-link {
            margin-top: 1.5rem;
            padding-top: 1.5rem;
            border-top: 1px solid var(--border);
            color: var(--accent);
            font-weight: 500;
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            transition: gap 0.3s ease;
        }

        .project-link:hover {
            gap: 0.75rem;
        }

        /* CONTACT */
        .contact {
            text-align: center;
            background: var(--surface);
            padding: 3rem;
            border-radius: 12px;
            border: 1px solid var(--border);
        }

        .contact h2 {
            font-size: 2rem;
            margin-bottom: 1.5rem;
        }

        .contact p {
            color: var(--text-secondary);
            margin-bottom: 2rem;
            font-size: 1.05rem;
        }

        .social-links {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
        }

        .social-btn {
            width: 50px;
            height: 50px;
            border: 1px solid var(--border);
            background: var(--bg);
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: all 0.3s;
            color: var(--text-secondary);
        }

        .social-btn:hover {
            border-color: var(--accent);
            color: var(--accent);
            background: rgba(0, 217, 255, 0.05);
        }

        /* RESPONSIVE */
        @media (max-width: 768px) {
            section {
                padding: 3rem 0;
            }

            .hero {
                min-height: 80vh;
            }

            .hero h1 {
                font-size: 2rem;
            }

            .about {
                grid-template-columns: 1fr;
                gap: 2rem;
            }

            .avatar-section {
                height: 300px;
            }

            .tabs {
                flex-wrap: wrap;
            }

            .featured-grid {
                grid-template-columns: 1fr;
            }

            .cta-group {
                flex-direction: column;
            }

            .btn {
                width: 100%;
            }
        }
    </style>
</head>
<body>
    <!-- HERO -->
    <section class="hero">
        <div class="hero-content">
            <div class="hero-badge">Embedded Systems & Firmware Engineering</div>
            <h1>I build <span class="highlight">firmware</span> that works on real hardware</h1>
            <p>Bare-metal embedded C/C++, hardware bring-up, real-time systems. From microcontroller drivers to hardware-software integration.</p>
            <div class="cta-group">
                <button class="btn btn-primary" onclick="document.getElementById('projects').scrollIntoView({behavior: 'smooth'})">See My Work</button>
                <a href="https://github.com/varunkumar898" target="_blank" class="btn btn-secondary">GitHub</a>
            </div>
        </div>
    </section>

    <!-- ABOUT -->
    <section class="container about">
        <div class="about-text">
            <h2>About</h2>
            <p>I focus on low-level systems that bridge hardware and software. Whether it's bringing up a new board, writing deterministic firmware, or debugging with an oscilloscope, I enjoy working close to the metal.</p>
            <p>Experience across ARM Cortex-M (STM32, NXP) and RISC-V architectures. Comfortable with hardware schematics, PCB validation, and collaborating with hardware teams to solve real-world problems.</p>
            <p style="color: var(--accent); margin-top: 2rem; font-weight: 500;">→ Currently exploring: Advanced peripheral protocols, FreeRTOS optimization, hardware-software co-design patterns</p>
        </div>
        <div class="avatar-section">
            <img src="https://avatars.githubusercontent.com/u/175243904?s=400" alt="Varun Kumar" class="avatar">
        </div>
    </section>

    <!-- TECH STACK -->
    <section class="container tech-section">
        <h2>Tech Stack</h2>
        
        <div class="tabs">
            <button class="tab-btn active" onclick="switchTab(event, 'languages')">💻 Languages & Firmware</button>
            <button class="tab-btn" onclick="switchTab(event, 'architecture')">⚙️ Systems & Architecture</button>
            <button class="tab-btn" onclick="switchTab(event, 'protocols')">📡 Protocols & Connectivity</button>
            <button class="tab-btn" onclick="switchTab(event, 'hardware')">🎨 Hardware & PCB</button>
            <button class="tab-btn" onclick="switchTab(event, 'tools')">🛠 Debugging & Tools</button>
        </div>

        <!-- Languages & Firmware -->
        <div id="languages" class="tab-content active">
            <div class="tech-card">
                <div class="tech-emoji">C</div>
                <div class="tech-name">Embedded C</div>
                <div class="tech-desc">Bare-metal firmware, drivers, optimized for ARM Cortex-M and RISC-V</div>
            </div>
            <div class="tech-card">
                <div class="tech-emoji">⚡</div>
                <div class="tech-name">C++</div>
                <div class="tech-desc">Modern C++ for embedded systems, template metaprogramming</div>
            </div>
            <div class="tech-card">
                <div class="tech-emoji">🐍</div>
                <div class="tech-name">Python</div>
                <div class="tech-desc">Hardware testing scripts, firmware analysis, automation</div>
            </div>
            <div class="tech-card">
                <div class="tech-emoji">🔧</div>
                <div class="tech-name">Assembly</div>
                <div class="tech-desc">ARM Thumb ISA, startup code, performance-critical sections</div>
            </div>
        </div>

        <!-- Systems & Architecture -->
        <div id="architecture" class="tab-content">
            <div class="tech-card">
                <div class="tech-emoji">📌</div>
                <div class="tech-name">ARM Cortex-M</div>
                <div class="tech-desc">STM32F0/F1/F4/H7, NXP LPC, full register-level programming</div>
            </div>
            <div class="tech-card">
                <div class="tech-emoji">⛓️</div>
                <div class="tech-name">RISC-V</div>
                <div class="tech-desc">Open ISA architecture, modular instruction sets, emerging ecosystem</div>
            </div>
            <div class="tech-card">
                <div class="tech-emoji">🔄</div>
                <div class="tech-name">FreeRTOS</div>
                <div class="tech-desc">Task scheduling, synchronization primitives, real-time constraints</div>
            </div>
            <div class="tech-card">
                <div class="tech-emoji">⏱️</div>
                <div class="tech-name">Real-Time Systems</div>
                <div class="tech-desc">Deterministic behavior, interrupt handling, timing guarantees</div>
            </div>
        </div>

        <!-- Protocols & Connectivity -->
        <div id="protocols" class="tab-content">
            <div class="tech-card">
                <div class="tech-emoji">📝</div>
                <div class="tech-name">UART/Serial</div>
                <div class="tech-desc">Asynchronous serial, DMA transfers, flow control</div>
            </div>
            <div class="tech-card">
                <div class="tech-emoji">🎯</div>
                <div class="tech-name">SPI</div>
                <div class="tech-desc">High-speed synchronous protocol, peripheral interfaces</div>
            </div>
            <div class="tech-card">
                <div class="tech-emoji">🔗</div>
                <div class="tech-name">I2C/TWI</div>
                <div class="tech-desc">Two-wire protocol, sensor/peripheral communication</div>
            </div>
            <div class="tech-card">
                <div class="tech-emoji">🚌</div>
                <div class="tech-name">CAN & Modbus</div>
                <div class="tech-desc">CAN bus, Modbus RTU/TCP for industrial systems</div>
            </div>
        </div>

        <!-- Hardware & PCB -->
        <div id="hardware" class="tab-content">
            <div class="tech-card">
                <div class="tech-emoji">📊</div>
                <div class="tech-name">Schematic Design</div>
                <div class="tech-desc">Circuit design, power delivery, signal integrity</div>
            </div>
            <div class="tech-card">
                <div class="tech-emoji">🖥️</div>
                <div class="tech-name">PCB Layout</div>
                <div class="tech-desc">Routing, layer stackup, thermal management, EMC/EMI</div>
            </div>
            <div class="tech-card">
                <div class="tech-emoji">✅</div>
                <div class="tech-name">Board Bring-up</div>
                <div class="tech-desc">Hardware validation, bootloader development, first-boot debugging</div>
            </div>
            <div class="tech-card">
                <div class="tech-emoji">⚙️</div>
                <div class="tech-name">Peripheral Drivers</div>
                <div class="tech-desc">GPIO, ADC, PWM, timers, DMA, clock configuration</div>
            </div>
        </div>

        <!-- Debugging & Tools -->
        <div id="tools" class="tab-content">
            <div class="tech-card">
                <div class="tech-emoji">🔌</div>
                <div class="tech-name">Debugging Hardware</div>
                <div class="tech-desc">JTAG, SWD, GDB, J-Link, ST-Link, oscilloscope, logic analyzer</div>
            </div>
            <div class="tech-card">
                <div class="tech-emoji">🛠️</div>
                <div class="tech-name">Development Tools</div>
                <div class="tech-desc">STM32CubeIDE, ARM Keil, GCC ARM toolchain, VS Code</div>
            </div>
            <div class="tech-card">
                <div class="tech-emoji">📈</div>
                <div class="tech-name">Profiling & Analysis</div>
                <div class="tech-desc">Performance monitoring, memory usage, stack analysis</div>
            </div>
            <div class="tech-card">
                <div class="tech-emoji">📦</div>
                <div class="tech-name">Build & Version Control</div>
                <div class="tech-desc">CMake, Make, Git, continuous integration for firmware</div>
            </div>
        </div>
    </section>

    <!-- FEATURED PROJECTS -->
    <section class="container" id="projects">
        <div class="featured-header">
            <h2>Featured Projects</h2>
            <p>Real hardware, real problems, real solutions</p>
        </div>
        <div class="featured-grid">
            <a href="https://github.com/varunkumar898/Driver-for-STM32F030x4-x6-x8-xC" target="_blank" class="project-card">
                <div class="project-icon">⚙️</div>
                <div class="project-name">STM32 Bare-Metal Drivers</div>
                <div class="project-description">Custom peripheral drivers for STM32F030 from scratch. GPIO, RCC, NVIC, EXTI, ADC, I2C, SPI implementations without HAL abstraction.</div>
                <div class="project-tags">
                    <span class="tag">C</span>
                    <span class="tag">ARM Cortex-M0</span>
                    <span class="tag">Drivers</span>
                </div>
                <div class="project-link">View Code →</div>
            </a>

            <a href="https://github.com/varunkumar898/Hand-detection-using-open-cv" target="_blank" class="project-card">
                <div class="project-icon">🎯</div>
                <div class="project-name">Hand Detection Pipeline</div>
                <div class="project-description">Real-time computer vision system for hand landmark detection using OpenCV. Demonstrates low-latency processing on constrained hardware.</div>
                <div class="project-tags">
                    <span class="tag">Python</span>
                    <span class="tag">OpenCV</span>
                    <span class="tag">Real-time</span>
                </div>
                <div class="project-link">View Code →</div>
            </a>

            <a href="https://github.com/varunkumar898/Smart-parking-system" target="_blank" class="project-card">
                <div class="project-icon">🅿️</div>
                <div class="project-name">Smart Parking System</div>
                <div class="project-description">End-to-end IoT system combining embedded sensors, edge processing, and backend services. Hardware integration, firmware, and system architecture.</div>
                <div class="project-tags">
                    <span class="tag">Embedded</span>
                    <span class="tag">IoT</span>
                    <span class="tag">Systems</span>
                </div>
                <div class="project-link">View Code →</div>
            </a>

            <a href="https://github.com/varunkumar898/onnx-model" target="_blank" class="project-card">
                <div class="project-icon">🧠</div>
                <div class="project-name">ONNX Model Optimization</div>
                <div class="project-description">ML model conversion and optimization for embedded deployment. Reduced model size and latency for resource-constrained devices.</div>
                <div class="project-tags">
                    <span class="tag">Python</span>
                    <span class="tag">ML</span>
                    <span class="tag">ONNX</span>
                </div>
                <div class="project-link">View Code →</div>
            </a>

            <a href="https://github.com/varunkumar898/eleven-labs-to-assistant" target="_blank" class="project-card">
                <div class="project-icon">🎤</div>
                <div class="project-name">Voice AI Integration</div>
                <div class="project-description">Real-time voice synthesis and conversational AI using Eleven Labs. Explores hardware-software co-design for voice applications.</div>
                <div class="project-tags">
                    <span class="tag">Python</span>
                    <span class="tag">AI</span>
                    <span class="tag">Voice</span>
                </div>
                <div class="project-link">View Code →</div>
            </a>

            <a href="https://github.com/varunkumar898/test-eleven-labs" target="_blank" class="project-card">
                <div class="project-icon">🔊</div>
                <div class="project-name">Voice API Experimentation</div>
                <div class="project-description">Testing and validation framework for voice synthesis APIs. Benchmarking latency, quality, and integration patterns for embedded use.</div>
                <div class="project-tags">
                    <span class="tag">Python</span>
                    <span class="tag">API</span>
                    <span class="tag">Testing</span>
                </div>
                <div class="project-link">View Code →</div>
            </a>
        </div>
    </section>

    <!-- CONTACT -->
    <section class="container" style="padding: 5rem 0;">
        <div class="contact">
            <h2>Let's Work Together</h2>
            <p>Open to hardware bring-up, firmware architecture, and embedded systems projects.</p>
            <div class="social-links">
                <a href="https://github.com/varunkumar898" target="_blank" class="social-btn" title="GitHub">
                    <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
                        <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.6.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v 3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
                    </svg>
                </a>
                <a href="mailto:varunvenkat2020@gmail.com" class="social-btn" title="Email">
                    <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                        <rect x="2" y="4" width="20" height="16" rx="2"></rect>
                        <path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7"></path>
                    </svg>
                </a>
                <a href="https://linkedin.com" target="_blank" class="social-btn" title="LinkedIn">
                    <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
                        <path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/>
                    </svg>
                </a>
            </div>
        </div>
    </section>

    <script>
        function switchTab(event, tabName) {
            // Hide all tabs
            document.querySelectorAll('.tab-content').forEach(tab => {
                tab.classList.remove('active');
            });
            
            // Remove active from all buttons
            document.querySelectorAll('.tab-btn').forEach(btn => {
                btn.classList.remove('active');
            });
            
            // Show selected tab
            document.getElementById(tabName).classList.add('active');
            event.target.classList.add('active');
        }

        // Add hover animations to tech cards
        document.querySelectorAll('.tech-card').forEach(card => {
            card.addEventListener('mouseenter', function() {
                this.style.transform = 'translateY(-4px)';
            });
            card.addEventListener('mouseleave', function() {
                this.style.transform = 'translateY(0)';
            });
        });
    </script>
</body>
</html>
