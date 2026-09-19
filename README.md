# Varun Kumar — Embedded Systems & Firmware Engineering

Welcome. I build firmware that works on real hardware.

## What I Do
- **Bare-metal firmware** in Embedded C/C++ for ARM Cortex-M (STM32) and RISC-V
- **Hardware bring-up**: Peripheral drivers (GPIO, ADC, SPI, I2C, CAN, UART), debugging with oscilloscopes and logic analyzers
- **Real-time systems**: FreeRTOS task scheduling, thread-safe synchronization, deterministic behavior
- **Communication protocols**: UART, SPI, I2C, CAN, Modbus RTU/TCP
- **Cross-functional work**: Hardware schematics, PCB validation, board-level testing, working with hardware teams
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Varun Kumar - GitHub Portfolio</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #0d1117;
            --secondary: #161b22;
            --accent: #58a6ff;
            --accent-hover: #79c0ff;
            --text: #c9d1d9;
            --text-dim: #8b949e;
            --border: #30363d;
            --success: #3fb950;
            --warning: #d29922;
        }

        body {
            background: linear-gradient(135deg, var(--primary) 0%, #0a0e27 100%);
            color: var(--text);
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
            line-height: 1.6;
            min-height: 100vh;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
        }

        /* Header Section */
        .header {
            display: grid;
            grid-template-columns: 140px 1fr;
            gap: 2rem;
            margin-bottom: 3rem;
            padding: 2rem;
            background: var(--secondary);
            border: 1px solid var(--border);
            border-radius: 12px;
            align-items: start;
        }

        .avatar {
            width: 140px;
            height: 140px;
            border-radius: 50%;
            border: 3px solid var(--accent);
            object-fit: cover;
            box-shadow: 0 0 20px rgba(88, 166, 255, 0.3);
        }

        .header-info h1 {
            font-size: 2.5rem;
            margin-bottom: 0.5rem;
            color: var(--text);
        }

        .github-handle {
            color: var(--text-dim);
            font-size: 1.1rem;
            margin-bottom: 1rem;
        }

        .stats {
            display: flex;
            gap: 2rem;
            margin-bottom: 1.5rem;
        }

        .stat {
            display: flex;
            flex-direction: column;
        }

        .stat-value {
            font-size: 1.8rem;
            font-weight: 600;
            color: var(--accent);
        }

        .stat-label {
            font-size: 0.9rem;
            color: var(--text-dim);
        }

        .bio {
            color: var(--text);
            line-height: 1.7;
            margin-bottom: 1rem;
        }

        .links {
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
        }

        .link-btn {
            padding: 0.5rem 1rem;
            background: var(--accent);
            color: var(--primary);
            text-decoration: none;
            border-radius: 6px;
            font-weight: 500;
            font-size: 0.9rem;
            transition: all 0.3s;
            border: none;
            cursor: pointer;
        }

        .link-btn:hover {
            background: var(--accent-hover);
            transform: translateY(-2px);
        }

        .link-btn.secondary {
            background: transparent;
            border: 1px solid var(--accent);
            color: var(--accent);
        }

        .link-btn.secondary:hover {
            background: rgba(88, 166, 255, 0.1);
        }

        /* Filters */
        .filters {
            display: flex;
            gap: 1rem;
            margin-bottom: 2rem;
            flex-wrap: wrap;
        }

        .filter-btn {
            padding: 0.6rem 1.2rem;
            background: var(--secondary);
            border: 1px solid var(--border);
            color: var(--text);
            border-radius: 6px;
            cursor: pointer;
            transition: all 0.3s;
            font-size: 0.95rem;
        }

        .filter-btn:hover {
            border-color: var(--accent);
            color: var(--accent);
        }

        .filter-btn.active {
            background: var(--accent);
            border-color: var(--accent);
            color: var(--primary);
        }

        /* Repos Grid */
        .repos-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
            gap: 1.5rem;
            margin-bottom: 3rem;
        }

        .repo-card {
            background: var(--secondary);
            border: 1px solid var(--border);
            border-radius: 12px;
            padding: 1.5rem;
            transition: all 0.3s;
            cursor: pointer;
            text-decoration: none;
            color: inherit;
            display: flex;
            flex-direction: column;
        }

        .repo-card:hover {
            border-color: var(--accent);
            box-shadow: 0 8px 24px rgba(88, 166, 255, 0.2);
            transform: translateY(-4px);
        }

        .repo-name {
            font-size: 1.2rem;
            font-weight: 600;
            color: var(--accent);
            margin-bottom: 0.5rem;
            word-break: break-word;
        }

        .repo-description {
            color: var(--text-dim);
            margin-bottom: 1rem;
            font-size: 0.95rem;
            flex-grow: 1;
        }

        .repo-meta {
            display: flex;
            gap: 1.5rem;
            align-items: center;
            flex-wrap: wrap;
            padding-top: 1rem;
            border-top: 1px solid var(--border);
            font-size: 0.85rem;
        }

        .language {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            color: var(--text-dim);
        }

        .language-dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
        }

        .stars {
            display: flex;
            align-items: center;
            gap: 0.3rem;
            color: var(--warning);
        }

        .forks {
            display: flex;
            align-items: center;
            gap: 0.3rem;
            color: var(--text-dim);
        }

        /* Loading & Empty States */
        .loading {
            text-align: center;
            padding: 3rem;
            color: var(--text-dim);
        }

        .spinner {
            border: 3px solid var(--border);
            border-top: 3px solid var(--accent);
            border-radius: 50%;
            width: 40px;
            height: 40px;
            animation: spin 1s linear infinite;
            margin: 0 auto 1rem;
        }

        @keyframes spin {
            to { transform: rotate(360deg); }
        }

        .error {
            background: rgba(248, 81, 73, 0.1);
            border: 1px solid #f85149;
            padding: 1.5rem;
            border-radius: 8px;
            color: #f85149;
            margin-bottom: 2rem;
        }

        .topics {
            display: flex;
            gap: 0.5rem;
            flex-wrap: wrap;
            margin-bottom: 1rem;
        }

        .topic-tag {
            background: rgba(88, 166, 255, 0.15);
            color: var(--accent);
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.8rem;
        }

        @media (max-width: 768px) {
            .header {
                grid-template-columns: 1fr;
                text-align: center;
            }

            .header-info h1 {
                font-size: 1.8rem;
            }

            .stats {
                justify-content: center;
            }

            .repos-grid {
                grid-template-columns: 1fr;
            }

            .links {
                justify-content: center;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Header -->
        <div class="header" id="header">
            <div class="loading">
                <div class="spinner"></div>
                Loading profile...
            </div>
        </div>

        <!-- Filters -->
        <div class="filters" id="filters"></div>

        <!-- Repos -->
        <div id="error"></div>
        <div class="repos-grid" id="repos">
            <div class="loading">
                <div class="spinner"></div>
                Fetching repositories...
            </div>
        </div>
    </div>

    <script>
        const GITHUB_USER = 'varunkumar898';
        const API_BASE = 'https://api.github.com';

        // Language colors mapping
        const languageColors = {
            Python: '#3572A5',
            C: '#555555',
            JavaScript: '#f1e05a',
            TypeScript: '#3178c6',
            Java: '#b07219',
            'C++': '#f34b7d',
            Go: '#00ADD8',
            Rust: '#ce422b',
            HTML: '#e34c26',
            CSS: '#563d7c',
            PHP: '#777bb4',
            Ruby: '#cc342d',
            Shell: '#89e051'
        };

        let allRepos = [];
        let filteredRepos = [];

        async function fetchUserData() {
            try {
                const userRes = await fetch(`${API_BASE}/users/${GITHUB_USER}`);
                const user = await userRes.json();
                renderHeader(user);
                return user;
            } catch (error) {
                showError('Failed to load user data');
                console.error(error);
            }
        }

        async function fetchRepositories() {
            try {
                let repos = [];
                let page = 1;
                let hasMore = true;

                // Fetch all repos (paginated)
                while (hasMore && page <= 5) {
                    const res = await fetch(
                        `${API_BASE}/users/${GITHUB_USER}/repos?per_page=100&page=${page}&sort=updated`
                    );
                    const data = await res.json();
                    
                    if (!Array.isArray(data) || data.length === 0) {
                        hasMore = false;
                    } else {
                        repos = repos.concat(data);
                        page++;
                    }
                }

                allRepos = repos;
                filteredRepos = repos;
                renderRepositories(repos);
                renderFilters(repos);
            } catch (error) {
                showError('Failed to load repositories');
                console.error(error);
            }
        }

        function renderHeader(user) {
            const header = document.getElementById('header');
            header.innerHTML = `
                <img src="${user.avatar_url}" alt="${user.name}" class="avatar">
                <div class="header-info">
                    <h1>${user.name || user.login}</h1>
                    <div class="github-handle">@${user.login}</div>
                    <div class="bio">${user.bio || 'Full-stack developer | Open source enthusiast'}</div>
                    <div class="stats">
                        <div class="stat">
                            <div class="stat-value">${user.public_repos}</div>
                            <div class="stat-label">Repositories</div>
                        </div>
                        <div class="stat">
                            <div class="stat-value">${user.followers}</div>
                            <div class="stat-label">Followers</div>
                        </div>
                        <div class="stat">
                            <div class="stat-value">${user.following}</div>
                            <div class="stat-label">Following</div>
                        </div>
                    </div>
                    <div class="links">
                        <a href="https://github.com/${user.login}" target="_blank" class="link-btn">View on GitHub</a>
                        ${user.blog ? `<a href="${user.blog}" target="_blank" class="link-btn secondary">Website</a>` : ''}
                        ${user.twitter_username ? `<a href="https://twitter.com/${user.twitter_username}" target="_blank" class="link-btn secondary">Twitter</a>` : ''}
                    </div>
                </div>
            `;
        }

        function renderFilters(repos) {
            const filters = document.getElementById('filters');
            const languages = new Set();
            
            repos.forEach(repo => {
                if (repo.language) languages.add(repo.language);
            });

            let html = '<button class="filter-btn active" onclick="filterRepos(null)">All Repos</button>';
            
            Array.from(languages).sort().forEach(lang => {
                html += `<button class="filter-btn" onclick="filterRepos('${lang}')">${lang}</button>`;
            });

            filters.innerHTML = html;
        }

        function filterRepos(language) {
            // Update active button
            document.querySelectorAll('.filter-btn').forEach(btn => btn.classList.remove('active'));
            event.target.classList.add('active');

            // Filter repos
            if (language === null) {
                filteredRepos = allRepos;
            } else {
                filteredRepos = allRepos.filter(repo => repo.language === language);
            }

            renderRepositories(filteredRepos);
        }

        function renderRepositories(repos) {
            const reposContainer = document.getElementById('repos');
            
            if (repos.length === 0) {
                reposContainer.innerHTML = '<div class="loading">No repositories found</div>';
                return;
            }

            let html = repos.map(repo => `
                <a href="${repo.html_url}" target="_blank" class="repo-card">
                    <div class="repo-name">${repo.name}</div>
                    ${repo.topics && repo.topics.length > 0 ? `
                        <div class="topics">
                            ${repo.topics.slice(0, 3).map(topic => `<span class="topic-tag">${topic}</span>`).join('')}
                        </div>
                    ` : ''}
                    <div class="repo-description">${repo.description || 'No description provided'}</div>
                    <div class="repo-meta">
                        ${repo.language ? `
                            <div class="language">
                                <div class="language-dot" style="background-color: ${languageColors[repo.language] || '#858585'}"></div>
                                ${repo.language}
                            </div>
                        ` : ''}
                        ${repo.stargazers_count > 0 ? `
                            <div class="stars">
                                ⭐ ${repo.stargazers_count}
                            </div>
                        ` : ''}
                        ${repo.forks_count > 0 ? `
                            <div class="forks">
                                🔀 ${repo.forks_count}
                            </div>
                        ` : ''}
                    </div>
                </a>
            `).join('');

            reposContainer.innerHTML = html;
        }

        function showError(message) {
            const errorDiv = document.getElementById('error');
            errorDiv.innerHTML = `<div class="error">${message}</div>`;
        }

        // Initialize
        fetchUserData();
        fetchRepositories();
    </script>
</body>
</html>
## Highlighted Projects

### [STM32F030 Hardware Abstraction Layer](https://github.com/varunkumarjob898/Driver-for-STM32F030x4-x6-x8-xC)
Production-ready bare-metal drivers (GPIO, RCC, NVIC, ADC, SPI, I2C). Proves I can read datasheets, 
write register-level code, and validate on real hardware.

### [Smart-number-plating](https://github.com/varunkumar898/smart-number-plating)
FreeRTOS embedded system with real-time RFID packet handling, mutex-protected state, and 
deterministic interrupt processing.

## Experience
- **MindGrow** (Apr–Jun 2026): RISC-V firmware, Docker CI/CD toolchain, Modbus/CAN protocol implementation
- **MH Cockpit** (Jun–Oct 2025): IoT edge device firmware, sensor validation, hardware-firmware co-integration
- **TVS Sundram Fasteners** (Jan–Mar 2026): Technical documentation, OEM product CAD

## Skills at a Glance
Embedded C/C++ · ARM Cortex-M · RISC-V · FreeRTOS · Bare-metal · Debuggers (GDB, OpenOCD, JTAG) · 
Oscilloscope & Logic Analyzer · Git · Docker · Jenkins · Makefiles · Communication Protocols (UART/SPI/I2C/CAN)

## Get In Touch
- **Email**: varunkumarjob2004@gmail.com
- **LinkedIn**: [linkedin.com/in/varun-kumarjob8055](https://linkedin.com/in/varun-kumarjob8055)

---

*Graduating June 2026. Open to embedded systems, firmware, and IoT roles in Chennai and remote.*
## 🔧 Tech Stack

### 💻 Languages & Firmware
![Embedded C](https://img.shields.io/badge/Embedded%20C-00599C?style=flat-square&logo=c&logoColor=white)
![Embedded C++](https://img.shields.io/badge/Embedded%20C%2B%2B-00599C?style=flat-square&logo=cplusplus&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Bare-Metal](https://img.shields.io/badge/Bare--Metal%20Programming-00599C?style=flat-square)
![STM32](https://img.shields.io/badge/STM32%20(F0%2F%20H7)-03234B?style=flat-square&logo=stmicroelectronics&logoColor=white)

### ⚙️ Systems & Architecture
![FreeRTOS](https://img.shields.io/badge/FreeRTOS-16808C?style=flat-square&logo=freertos&logoColor=white)
![Real-Time Systems](https://img.shields.io/badge/Real--Time%20Systems-00599C?style=flat-square)
![IoT Systems Design](https://img.shields.io/badge/IoT%20Systems%20Design-129900?style=flat-square)
![Electrical Engineering](https://img.shields.io/badge/Electrical%20Engineering-00599C?style=flat-square)

### 📡 Protocols & Connectivity
![I2C / SPI / UART / CAN](https://img.shields.io/badge/Protocols-I2C%20%7C%20SPI%20%7C%20UART%20%7C%20CAN-00599C?style=flat-square)
![BLE](https://img.shields.io/badge/BLE-0082FC?style=flat-square&logo=bluetooth&logoColor=white)
![MQTT](https://img.shields.io/badge/MQTT-660066?style=flat-square&logo=mqtt&logoColor=white)
![Modbus](https://img.shields.io/badge/Modbus-RTU%20%2F%20TCP-E3120B?style=flat-square)

### 🎨 Hardware & PCB Design
![Altium Designer](https://img.shields.io/badge/Altium%20Designer-A5915F?style=flat-square&logo=altiumdesigner&logoColor=white)
![KiCad](https://img.shields.io/badge/KiCad-31419B?style=flat-square&logo=kicad&logoColor=white)

### 🛠 Debugging, Tools & DevOps
![GDB](https://img.shields.io/badge/GDB-003B5C?style=flat-square&logo=gnu&logoColor=white)
![GCC Toolchain](https://img.shields.io/badge/GCC%20Toolchain-46505A?style=flat-square&logo=gnu&logoColor=white)
![OpenOCD](https://img.shields.io/badge/OpenOCD-2C3E50?style=flat-square)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Jenkins](https://img.shields.io/badge/Jenkins-D24939?style=flat-square&logo=jenkins&logoColor=white)
![Microsoft Excel](https://img.shields.io/badge/Microsoft%20Excel-217346?style=flat-square&logo=microsoftexcel&logoColor=white)
<!--
**varunkumar898/varunkumar898** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
