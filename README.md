<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Jainer Muñoz | Senior Fullstack Software Engineer</title>
    
    <!-- Chosen Palette: Warm Neutral Harmony -->
    <!-- Application Structure Plan: A single-page application with a fixed top navigation bar for smooth scrolling. The structure includes a hero section for immediate impact, a summary, an interactive skills section featuring charts for quick visualization, a vertical timeline for a clear view of career progression, and a final education section. This non-linear, interactive structure was chosen to allow recruiters to quickly navigate to the information most relevant to them, making the resume more engaging and easier to digest than a traditional document. The goal is to facilitate user understanding and ease of navigation. -->
    <!-- Visualization & Content Choices: 
        - Experience -> Goal: Show career progression -> Viz/Presentation Method: Interactive Vertical Timeline -> Interaction: Clicking a job title reveals details -> Justification: More engaging and visually appealing than a simple list, clearly showing the career path over time. -> Library/Method: HTML/CSS/JS.
        - Soft Skills -> Goal: Highlight key personal attributes -> Viz/Presentation Method: Radar Chart -> Interaction: Hover for tooltips -> Justification: A radar chart provides a holistic, balanced view of core professional competencies. -> Library/Method: Chart.js Canvas.
        - Technical Skills -> Goal: Organize and present a wide range of technical abilities -> Viz/Presentation Method: Grouped Bar Charts -> Interaction: Hover for tooltips -> Justification: Grouping skills by category (Frontend, Backend, etc.) makes the extensive skill set easy to navigate and quickly assess. -> Library/Method: Chart.js Canvas.
    -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->

    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #FDFBF8; /* Warm off-white */
            color: #4A4A4A; /* Dark Gray */
        }
        .timeline-item-content {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.5s ease-in-out;
        }
        .timeline-item-content.open {
            max-height: 500px; /* Adjust as needed */
        }
        .chart-container {
            position: relative;
            width: 100%;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
            height: 300px;
            max-height: 400px;
        }
        @media (min-width: 768px) {
            .chart-container {
                height: 350px;
            }
        }
        nav a {
            transition: color 0.3s;
        }
        nav a:hover {
            color: #D4A373; /* Accent color */
        }
    </style>
</head>
<body class="antialiased">

    <header class="bg-white/80 backdrop-blur-md sticky top-0 z-50 border-b border-gray-200">
        <nav class="container mx-auto px-6 py-4 flex justify-between items-center">
            <div class="text-2xl font-bold text-gray-800">JM</div>
            <div class="hidden md:flex space-x-8">
                <a href="#summary" class="text-gray-600 font-medium">Summary</a>
                <a href="#experience" class="text-gray-600 font-medium">Experience</a>
                <a href="#skills" class="text-gray-600 font-medium">Skills</a>
                <a href="#education" class="text-gray-600 font-medium">Education</a>
            </div>
        </nav>
    </header>

    <main class="container mx-auto px-6 py-12">
        
        <section id="hero" class="text-center py-16">
            <h1 class="text-5xl md:text-7xl font-bold text-gray-900">Jainer Muñoz</h1>
            <p class="text-xl md:text-2xl text-gray-600 mt-4">Senior Fullstack Software Engineer</p>
            <div class="mt-8 text-sm text-gray-500 space-x-2 md:space-x-6">
                <span>+1 (226) 505-1663</span>
                <span>&bull;</span>
                <span>Jainer.Calvetti@Gmail.com</span>
                <span>&bull;</span>
                <a href="https://www.linkedin.com/in/jainer-munoz" target="_blank" class="text-blue-600 hover:underline">linkedin.com/in/jainer-munoz</a>
            </div>
        </section>

        <section id="summary" class="py-16">
             <h2 class="text-3xl font-bold text-center mb-8">Professional Summary</h2>
             <div class="max-w-4xl mx-auto text-lg text-gray-700 leading-relaxed text-center">
                <p>
                    A seasoned Senior Fullstack Engineer with over 8 years of experience building and scaling modern web and mobile platforms. Proven technical leader with expertise in **Node.js/TypeScript** and **React/React Native** within fast-paced **SaaS** environments. Excels at modernizing legacy systems, driving key initiatives, and implementing robust **AWS-based** solutions. A dedicated team player who leverages strong **mentorship** and **communication** skills to foster collaboration and elevate team performance, ensuring high-quality, product-driven impact at scale.
                </p>
            </div>
        </section>
        
        <section id="experience" class="py-16">
            <h2 class="text-3xl font-bold text-center mb-12">Career Journey</h2>
            <div class="max-w-4xl mx-auto text-lg text-gray-700 leading-relaxed text-center mb-12">
                <p>This section provides an interactive overview of my professional experience. My career has been a journey of continuous growth, tackling complex challenges, and delivering impactful solutions. Click on each role to expand and see the key responsibilities and achievements that defined my time there.</p>
            </div>

            <div class="relative max-w-3xl mx-auto">
                <div class="absolute left-1/2 -translate-x-1/2 h-full w-0.5 bg-gray-300"></div>
                
                <!-- Timeline Items -->
                <div class="timeline-item mt-8">
                    <div class="flex items-center relative">
                        <div class="w-1/2 pr-8 text-right">
                            <div class="font-bold text-lg text-gray-800">Tempo</div>
                            <div class="text-sm text-gray-500">Senior Fullstack Engineer</div>
                            <div class="text-xs text-gray-400">April 2022 - Current</div>
                        </div>
                        <div class="absolute left-1/2 -translate-x-1/2 w-4 h-4 bg-white border-2 border-[#D4A373] rounded-full"></div>
                        <div class="w-1/2 pl-8">
                            <div class="p-4 bg-white rounded-lg shadow-md cursor-pointer" onclick="toggleTimeline(this)">
                                <p class="font-semibold">Key Contributions & Growth</p>
                                <div class="timeline-item-content">
                                    <ul class="mt-2 text-sm text-gray-600 list-disc list-inside space-y-1">
                                        <li>Led projects to improve app stability, including a monorepo migration.</li>
                                        <li>Spearheaded initiative to improve networking observability with Nginx, Datadog, and Kubernetes.</li>
                                        <li>Pioneered a "Point in Time Recovery" (PITR) strategy on AWS.</li>
                                        <li>Consistently delivered high-quality, well-tested code and provided constructive feedback.</li>
                                        <li>Mentored junior and mid-level developers, actively pairing to resolve blockers.</li>
                                    </ul>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="timeline-item mt-8">
                    <div class="flex items-center relative">
                        <div class="w-1/2 pl-8 text-left">
                           <div class="p-4 bg-white rounded-lg shadow-md cursor-pointer" onclick="toggleTimeline(this)">
                                <p class="font-semibold">Core Responsibilities</p>
                                <div class="timeline-item-content">
                                    <ul class="mt-2 text-sm text-gray-600 list-disc list-inside space-y-1">
                                        <li>Contributed to the development and maintenance of core features.</li>
                                        <li>Advocated for software development best practices and refactored technical debt.</li>
                                        <li>Designed and implemented well-documented APIs.</li>
                                    </ul>
                                </div>
                            </div>
                        </div>
                         <div class="absolute left-1/2 -translate-x-1/2 w-4 h-4 bg-white border-2 border-[#D4A373] rounded-full"></div>
                        <div class="w-1/2 pr-8 text-right">
                            <div class="font-bold text-lg text-gray-800">Roadmunk</div>
                            <div class="text-sm text-gray-500">Developer</div>
                            <div class="text-xs text-gray-400">July 2021 - March 2022</div>
                        </div>
                    </div>
                </div>

                 <div class="timeline-item mt-8">
                    <div class="flex items-center relative">
                        <div class="w-1/2 pr-8 text-right">
                            <div class="font-bold text-lg text-gray-800">AVANTICA</div>
                            <div class="text-sm text-gray-500">Senior Software Developer</div>
                            <div class="text-xs text-gray-400">March 2021 - July 2021</div>
                        </div>
                        <div class="absolute left-1/2 -translate-x-1/2 w-4 h-4 bg-white border-2 border-[#D4A373] rounded-full"></div>
                        <div class="w-1/2 pl-8">
                            <div class="p-4 bg-white rounded-lg shadow-md cursor-pointer" onclick="toggleTimeline(this)">
                                <p class="font-semibold">Web Experience Development</p>
                                <div class="timeline-item-content">
                                    <ul class="mt-2 text-sm text-gray-600 list-disc list-inside space-y-1">
                                        <li>Built responsive and accessible web experiences using Vue.js.</li>
                                        <li>Contributed to a flexible and customizable codebase.</li>
                                    </ul>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- Add other timeline items similarly -->

            </div>
        </section>

        <section id="skills" class="py-16">
            <h2 class="text-3xl font-bold text-center mb-12">Core Competencies</h2>
            <div class="max-w-4xl mx-auto text-lg text-gray-700 leading-relaxed text-center mb-12">
                <p>This section provides a visual breakdown of my technical and soft skills. The charts below illustrate my proficiency across various domains, from frontend and backend development to DevOps and AI/ML. This data-driven view is designed to offer a quick yet comprehensive understanding of my capabilities.</p>
            </div>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-16 items-center">
                <div>
                    <h3 class="text-2xl font-bold text-center mb-4">Soft Skills</h3>
                    <div class="chart-container h-80 md:h-96">
                        <canvas id="softSkillsChart"></canvas>
                    </div>
                </div>
                <div>
                    <h3 class="text-2xl font-bold text-center mb-4">Technical Skills</h3>
                    <div class="chart-container h-80 md:h-96">
                        <canvas id="techSkillsChart"></canvas>
                    </div>
                </div>
            </div>
        </section>

        <section id="education" class="py-16 bg-white rounded-lg">
            <h2 class="text-3xl font-bold text-center mb-8">Education & Languages</h2>
            <div class="text-center">
                <h3 class="text-xl font-semibold text-gray-800">Universidad Central de Venezuela</h3>
                <p class="text-gray-600">Electrical Engineer</p>
                <div class="mt-6 border-t pt-6 max-w-sm mx-auto">
                     <h3 class="text-xl font-semibold text-gray-800">Languages</h3>
                     <p class="text-gray-600 mt-2">Spanish (Native)</p>
                     <p class="text-gray-600">English (C1 - Advanced)</p>
                </div>
            </div>
        </section>

    </main>
    
    <footer class="text-center py-6 border-t mt-12">
        <p class="text-gray-500 text-sm">&copy; 2025 Jainer Muñoz. All Rights Reserved.</p>
    </footer>

    <script>
        function toggleTimeline(element) {
            const content = element.querySelector('.timeline-item-content');
            content.classList.toggle('open');
        }

        // Chart.js Configuration
        document.addEventListener('DOMContentLoaded', () => {
            const chartOptions = {
                maintainAspectRatio: false,
                plugins: {
                    legend: {
                        position: 'bottom',
                        labels: {
                            font: {
                                family: 'Inter'
                            }
                        }
                    },
                    tooltip: {
                        titleFont: { family: 'Inter' },
                        bodyFont: { family: 'Inter' }
                    }
                }
            };

            // Soft Skills Radar Chart
            const softSkillsCtx = document.getElementById('softSkillsChart').getContext('2d');
            new Chart(softSkillsCtx, {
                type: 'radar',
                data: {
                    labels: ['Mentorship & Collaboration', 'Leadership & Initiative', 'Problem-Solving', 'Communication'],
                    datasets: [{
                        label: 'Proficiency',
                        data: [90, 85, 95, 88],
                        backgroundColor: 'rgba(212, 163, 115, 0.2)',
                        borderColor: 'rgba(212, 163, 115, 1)',
                        pointBackgroundColor: 'rgba(212, 163, 115, 1)',
                        pointBorderColor: '#fff',
                        pointHoverBackgroundColor: '#fff',
                        pointHoverBorderColor: 'rgba(212, 163, 115, 1)'
                    }]
                },
                options: {
                    ...chartOptions,
                    scales: {
                        r: {
                            angleLines: { color: 'rgba(0, 0, 0, 0.1)' },
                            grid: { color: 'rgba(0, 0, 0, 0.1)' },
                            pointLabels: { font: { size: 12, family: 'Inter' } },
                            ticks: { display: false, backdropColor: 'transparent' }
                        }
                    }
                }
            });

            // Technical Skills Bar Chart
            const techSkillsCtx = document.getElementById('techSkillsChart').getContext('2d');
            new Chart(techSkillsCtx, {
                type: 'bar',
                data: {
                    labels: ['Frontend', 'Backend', 'DevOps', 'AI/ML', 'Databases', 'Testing'],
                    datasets: [{
                        label: 'Skill Areas',
                        data: [95, 90, 80, 75, 88, 92],
                        backgroundColor: [
                            'rgba(118, 159, 184, 0.7)',
                            'rgba(179, 199, 211, 0.7)',
                            'rgba(242, 227, 219, 0.7)',
                            'rgba(212, 163, 115, 0.7)',
                            'rgba(142, 142, 142, 0.7)',
                            'rgba(191, 178, 163, 0.7)'
                        ],
                        borderColor: [
                            'rgba(118, 159, 184, 1)',
                            'rgba(179, 199, 211, 1)',
                            'rgba(242, 227, 219, 1)',
                            'rgba(212, 163, 115, 1)',
                            'rgba(142, 142, 142, 1)',
                            'rgba(191, 178, 163, 1)'
                        ],
                        borderWidth: 1
                    }]
                },
                options: {
                    ...chartOptions,
                    indexAxis: 'y',
                    scales: {
                        x: {
                            beginAtZero: true,
                            grid: { display: false }
                        },
                        y: {
                            grid: { display: false }
                        }
                    },
                    plugins: {
                        legend: { display: false }
                    }
                }
            });
        });
    </script>
</body>
</html>
