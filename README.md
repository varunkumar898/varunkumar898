<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Varun Kumar — Embedded Systems & Firmware Engineering</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Geist:wght@400;500;600;700&display=swap');

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --bg: #0f0f0f;
            --surface: #1a1a1a;
            --border: #333;
            --text: #f0f0f0;
            --text-secondary: #a0a0a0;
            --accent: #00d9ff;
        }

        body {
            background: var(--bg);
            color: var(--text);
            font-family: 'Geist', system-ui, -apple-system, sans-serif;
            line-height: 1.7;
            font-size: 16px;
        }

        a {
            color: var(--accent);
            text-decoration: none;
            transition: color 0.2s;
        }

        a:hover {
            color: #0099cc;
        }

        .container {
            max-width: 900px;
            margin: 0 auto;
            padding: 3rem 2rem;
        }

        /* HEADER */
        header {
            margin-bottom: 3rem;
            border-bottom: 1px solid var(--border);
            padding-bottom: 2rem;
        }

        h1 {
            font-size: 2.2rem;
            font-weight: 700;
            margin-bottom: 0.5rem;
            letter-spacing: -0.02em;
        }

        .tagline {
            color: var(--accent);
            font-size: 1.1rem;
            font-weight: 500;
            margin-bottom: 1rem;
        }

        /* SECTIONS */
        section {
            margin-bottom: 3rem;
        }

        h2 {
            font-size: 1.3rem;
            font-weight: 700;
            margin-bottom: 1.2rem;
            padding-bottom: 0.5rem;
            border-bottom: 1px solid var(--border);
        }

        /* WHAT I DO */
        .what-i-do ul {
            list-style: none;
            padding-left: 0;
        }

        .what-i-do li {
            margin-bottom: 0.9rem;
            color: var(--text-secondary);
            line-height: 1.8;
            padding-left: 1.5rem;
            position: relative;
        }

        .what-i-do li::before {
            content: '•';
            position: absolute;
            left: 0;
            color: var(--accent);
            font-weight: bold;
        }

        /* PROJECTS */
        .project {
            margin-bottom: 2.2rem;
            padding: 1.5rem;
            background: var(--surface);
            border-radius: 8px;
            border: 1px solid var(--border);
            transition: all 0.3s;
        }

        .project:hover {
            border-color: var(--accent);
            box-shadow: 0 8px 24px rgba(0, 217, 255, 0.1);
        }

        .project-title {
            font-size: 1.1rem;
            font-weight: 600;
            color: var(--accent);
            margin-bottom: 0.5rem;
        }

        .project-title a {
            color: var(--accent);
        }

        .project-title a:hover {
            color: #0099cc;
        }

        .project-description {
            color: var(--text-secondary);
            line-height: 1.8;
        }

        /* EXPERIENCE */
        .job {
            margin-bottom: 1.8rem;
            padding-left: 1.5rem;
            border-left: 2px solid var(--accent);
        }

        .job-title {
            font-weight: 600;
            color: var(--text);
            margin-bottom: 0.3rem;
        }

        .job-company {
            color: var(--accent);
            font-size: 0.95rem;
            font-weight: 500;
            margin-bottom: 0.5rem;
        }

        .job-description {
            color: var(--text-secondary);
            line-height: 1.7;
        }

        /* SKILLS */
        .skills-text {
            color: var(--text-secondary);
            line-height: 1.8;
            word-wrap: break-word;
        }

        .skills-text strong {
            color: var(--text);
            font-weight: 600;
        }

        /* CONTACT */
        .contact-section {
            background: var(--surface);
            padding: 2rem;
            border-radius: 8px;
            border: 1px solid var(--border);
        }

        .contact-item {
            margin-bottom: 1rem;
            display: flex;
            align-items: center;
            gap: 0.75rem;
        }

        .contact-item:last-child {
            margin-bottom: 0;
        }

        .contact-label {
            color: var(--text-secondary);
            min-width: 60px;
            font-size: 0.9rem;
        }

        .contact-value {
            color: var(--accent);
        }

        .closing-note {
            color: var(--text-secondary);
            margin-top: 2rem;
            padding-top: 1.5rem;
            border-top: 1px solid var(--border);
            font-size: 0.95rem;
            line-height: 1.7;
        }

        /* RESPONSIVE */
        @media (max-width: 640px) {
            .container {
                padding: 2rem 1rem;
            }

            h1 {
                font-size: 1.6rem;
            }

            h2 {
                font-size: 1.1rem;
            }

            .project {
                padding: 1rem;
            }

            .contact-item {
                flex-direction: column;
                align-items: flex-start;
            }
        }

        /* ACCESSIBILITY */
        *:focus-visible {
            outline: 2px solid var(--accent);
            outline-offset: 2px;
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- HEADER -->
        <header>
            <h1>Varun Kumar</h1>
            <div class="tagline">Embedded Systems & Firmware Engineering</div>
            <p style="color: var(--text-secondary); margin-top: 1rem;">Welcome. I build firmware that works on real hardware.</p>
        </header>

        <!-- WHAT I DO -->
        <section class="what-i-do">
            <h2>What I Do</h2>
            <ul>
                <li>Bare-metal firmware in Embedded C/C++ for ARM Cortex-M (STM32) and RISC-V</li>
                <li>Hardware bring-up: Peripheral drivers (GPIO, ADC, SPI, I2C, CAN, UART), debugging with oscilloscopes and logic analyzers</li>
                <li>Real-time systems: FreeRTOS task scheduling, thread-safe synchronization, deterministic behavior</li>
                <li>Communication protocols: UART, SPI, I2C, CAN, Modbus RTU/TCP</li>
                <li>Cross-functional work: Hardware schematics, PCB validation, board-level testing, working with hardware teams</li>
            </ul>
        </section>

        <!-- HIGHLIGHTED PROJECTS -->
        <section>
            <h2>Highlighted Projects</h2>
            
            <div class="project">
                <div class="project-title">
                    <a href="https://github.com/varunkumar898/Driver-for-STM32F030x4-x6-x8-xC" target="_blank">STM32F030 Hardware Abstraction Layer</a>
                </div>
                <div class="project-description">
                    Production-ready bare-metal drivers (GPIO, RCC, NVIC, ADC, SPI, I2C). Proves I can read datasheets, write register-level code, and validate on real hardware.
                </div>
            </div>

            <div class="project">
                <div class="project-title">
                    <a href="https://github.com/varunkumar898/Smart-parking-system" target="_blank">Smart Parking System</a>
                </div>
                <div class="project-description">
                    FreeRTOS embedded system with real-time sensor handling, mutex-protected state, and deterministic interrupt processing. End-to-end IoT solution.
                </div>
            </div>

            <div class="project">
                <div class="project-title">
                    <a href="https://github.com/varunkumar898/Hand-detection-using-open-cv" target="_blank">Real-Time Hand Detection Pipeline</a>
                </div>
                <div class="project-description">
                    Low-latency computer vision system using OpenCV. Demonstrates embedded vision on resource-constrained hardware with frame-rate optimization.
                </div>
            </div>
        </section>

        <!-- EXPERIENCE -->
        <section>
            <h2>Experience</h2>
            
            <div class="job">
                <div class="job-title">Firmware Engineer (Intern)</div>
                <div class="job-company">MindGrow</div>
                <div class="job-description">Apr–Jun 2026: RISC-V firmware development, Docker CI/CD toolchain setup, Modbus/CAN protocol implementation</div>
            </div>

            <div class="job">
                <div class="job-title">IoT Firmware Developer (Intern)</div>
                <div class="job-company">MH Cockpit</div>
                <div class="job-description">Jun–Oct 2025: IoT edge device firmware, sensor integration and validation, hardware-firmware co-integration</div>
            </div>

            <div class="job">
                <div class="job-title">Technical Documentation & CAD</div>
                <div class="job-company">TVS Sundram Fasteners</div>
                <div class="job-description">Jan–Mar 2026: Technical documentation, OEM product CAD design and validation</div>
            </div>
        </section>

        <!-- SKILLS -->
        <section>
            <h2>Skills at a Glance</h2>
            <p class="skills-text">
                <strong>Languages:</strong> Embedded C/C++ · Assembly<br>
                <strong>Architectures:</strong> ARM Cortex-M · RISC-V<br>
                <strong>RTOS & Systems:</strong> FreeRTOS · Bare-metal · Real-time scheduling<br>
                <strong>Protocols:</strong> UART · SPI · I2C · CAN · Modbus RTU/TCP<br>
                <strong>Debugging:</strong> GDB · OpenOCD · JTAG · SWD · Oscilloscope · Logic Analyzer<br>
                <strong>Tools & Infrastructure:</strong> Git · Docker · Jenkins · Makefiles · CMake · VS Code · STM32CubeIDE
            </p>
        </section>

        <!-- CONTACT -->
        <section class="contact-section">
            <h2 style="border: none; margin-bottom: 1.5rem;">Get In Touch</h2>
            
            <div class="contact-item">
                <div class="contact-label">Email</div>
                <div class="contact-value">
                    <a href="mailto:varunvenkat2020@gmail.com">varunvenkat2020@gmail.com</a>
                </div>
            </div>

            <div class="contact-item">
                <div class="contact-label">GitHub</div>
                <div class="contact-value">
                    <a href="https://github.com/varunkumar898" target="_blank">github.com/varunkumar898</a>
                </div>
            </div>

            <div class="contact-item">
                <div class="contact-label">LinkedIn</div>
                <div class="contact-value">
                    <a href="https://linkedin.com/in/varun-kumarjob8055" target="_blank">linkedin.com/in/varun-kumarjob8055</a>
                </div>
            </div>

            <div class="closing-note">
                Graduating June 2026. Open to embedded systems, firmware, and IoT roles in Chennai and remote. Excited about hardware bring-up, protocol implementation, and working on systems that operate at the edge of performance and reliability.
            </div>
        </section>
    </div>
</body>
</html>
