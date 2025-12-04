<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Resonance of Tuesday | System Diagnostic</title>
    
    <script src="https://cdn.tailwindcss.com"></script>
    
    <script src="https://unpkg.com/lucide@latest"></script>
    
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@100;400;700&family=Inter:wght@400;800&display=swap" rel="stylesheet">

    <style>
        /* === SYSTEM VARIABLES === */
        :root {
            --blueprint-blue: #0f172a;
            --grid-line: rgba(56, 189, 248, 0.1);
            --truth-green: #22c55e;
            --lie-orange: #f97316;
            --void-black: #020617;
            --blur-strength: 3px;
            --text-opacity: 0.7;
        }

        /* === HIGH FIDELITY STATE (Toggled via JS) === */
        body.high-fidelity {
            --blur-strength: 0px;
            --text-opacity: 1;
        }
        
        body {
            background-color: var(--blueprint-blue);
            color: #e2e8f0;
            font-family: 'JetBrains Mono', monospace;
            overflow-x: hidden;
            background-image: 
                linear-gradient(var(--grid-line) 1px, transparent 1px),
                linear-gradient(90deg, var(--grid-line) 1px, transparent 1px);
            background-size: 40px 40px;
        }

        /* === UTILITIES === */
        .technical-border {
            border: 1px solid var(--grid-line);
            position: relative;
        }
        
        .technical-border::after {
            content: '';
            position: absolute;
            bottom: -1px;
            right: -1px;
            width: 10px;
            height: 10px;
            border-bottom: 2px solid #38bdf8;
            border-right: 2px solid #38bdf8;
        }

        .blur-target {
            filter: blur(var(--blur-strength));
            opacity: var(--text-opacity);
            transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
        }

        /* === THE NINE MOONS ANIMATION === */
        .moon-queue {
            display: flex;
            align-items: center;
            gap: 20px;
            perspective: 1000px;
        }
        .moon {
            width: 20px;
            height: 20px;
            border-radius: 50%;
            border: 1px solid #64748b;
            background: #1e293b;
            box-shadow: 0 0 10px rgba(0,0,0,0.5);
            transition: all 0.5s ease;
        }
        .earth {
            width: 60px;
            height: 60px;
            border: 2px solid #38bdf8;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 10px;
            color: #38bdf8;
            box-shadow: 0 0 20px rgba(56, 189, 248, 0.2);
        }
        
        /* When High Fidelity is ON, the moons align */
        body.high-fidelity .moon-queue .moon {
            border-color: #e2e8f0;
            background: #f1f5f9;
            box-shadow: 0 0 15px rgba(255,255,255,0.3);
        }

        /* === THE FOREMAN CHAT === */
        #foreman-interface {
            position: fixed;
            bottom: 20px;
            right: 20px;
            width: 300px;
            background: rgba(15, 23, 42, 0.95);
            border: 1px solid #38bdf8;
            backdrop-filter: blur(10px);
            z-index: 50;
            font-size: 12px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
            transform: translateY(120%);
            transition: transform 0.5s cubic-bezier(0.34, 1.56, 0.64, 1);
        }
        #foreman-interface.active {
            transform: translateY(0);
        }
        .foreman-avatar {
            width: 40px;
            height: 40px;
            background: #38bdf8;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #0f172a;
            font-weight: bold;
        }

        /* === GLITCH EFFECT FOR "SOLD OUT" === */
        .glitch {
            position: relative;
            color: var(--lie-orange);
        }
        .glitch::before, .glitch::after {
            content: attr(data-text);
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
        }
        .glitch::before {
            left: 2px;
            text-shadow: -1px 0 red;
            clip: rect(24px, 550px, 90px, 0);
            animation: glitch-anim-2 3s infinite linear alternate-reverse;
        }
        .glitch::after {
            left: -2px;
            text-shadow: -1px 0 blue;
            clip: rect(85px, 550px, 140px, 0);
            animation: glitch-anim 2.5s infinite linear alternate-reverse;
        }
        @keyframes glitch-anim {
            0% { clip: rect(14px, 9999px, 127px, 0); }
            20% { clip: rect(80px, 9999px, 20px, 0); }
            40% { clip: rect(104px, 9999px, 86px, 0); }
            60% { clip: rect(3px, 9999px, 60px, 0); }
            80% { clip: rect(117px, 9999px, 18px, 0); }
            100% { clip: rect(122px, 9999px, 6px, 0); }
        }
    </style>
</head>
<body class="antialiased selection:bg-cyan-500 selection:text-white">

    <nav class="fixed top-0 w-full z-40 bg-slate-900/80 backdrop-blur border-b border-slate-700 h-12 flex items-center justify-between px-6 text-xs uppercase tracking-widest">
        <div class="flex items-center gap-4">
            <span class="text-cyan-400 font-bold">Resonance Engine v1.0</span>
            <span class="hidden md:inline text-slate-500">|</span>
            <span class="hidden md:inline text-slate-400">System Load: 11%</span>
        </div>
        <div class="flex items-center gap-2">
            <div id="status-indicator" class="w-2 h-2 rounded-full bg-orange-500 animate-pulse"></div>
            <span id="status-text" class="text-orange-500 font-bold">SIGNAL: LOW</span>
        </div>
    </nav>

    <section class="min-h-screen flex flex-col items-center justify-center relative pt-20 pb-20 overflow-hidden">
        
        <div class="moon-queue mb-12 opacity-80" id="moon-diagram">
            <div class="earth">EARTH</div>
            <div class="moon"></div>
            <div class="moon"></div>
            <div class="moon"></div>
            <div class="moon"></div>
            <div class="moon"></div>
            <div class="moon"></div>
            <div class="moon"></div>
            <div class="moon"></div>
            <div class="moon"></div>
        </div>

        <div class="z-10 mb-8">
            <label class="relative inline-flex items-center cursor-pointer group">
                <input type="checkbox" id="signal-toggle" class="sr-only peer">
                <div class="w-64 h-12 bg-slate-800 border-2 border-slate-600 rounded-sm peer-focus:outline-none peer-focus:ring-2 peer-focus:ring-cyan-400 flex items-center px-1 transition-all duration-500 group-hover:border-slate-400">
                    <div class="absolute left-4 text-xs font-bold text-slate-500 tracking-widest">LOW FIDELITY</div>
                    <div class="absolute right-4 text-xs font-bold text-cyan-400 tracking-widest opacity-0 peer-checked:opacity-100 transition-opacity">HIGH FIDELITY</div>
                    <div class="w-1/2 h-8 bg-slate-500 rounded-sm shadow-md transform transition-transform duration-300 peer-checked:translate-x-full peer-checked:bg-cyan-500"></div>
                </div>
            </label>
        </div>

        <div class="max-w-4xl px-6 text-center z-10">
            <h1 class="text-4xl md:text-7xl font-bold mb-6 tracking-tighter blur-target" id="hero-title">
                The Resonance of Tuesday
            </h1>
            
            <p class="text-xl md:text-2xl text-slate-400 mb-10 leading-relaxed blur-target" id="hero-logline">
                A charming story about a man who fixes kettles and finds friendship in a sleepy English village. Perfect for fans of light reading.
            </p>

            <div class="flex flex-col sm:flex-row gap-4 justify-center items-center">
                <a href="#read" class="px-8 py-4 bg-slate-800 hover:bg-slate-700 border border-slate-600 text-white font-mono text-sm uppercase tracking-widest transition-all technical-border">
                    <i data-lucide="file-text" class="inline w-4 h-4 mr-2"></i> Access Log Files
                </a>
                <a href="#buy" class="px-8 py-4 bg-cyan-600 hover:bg-cyan-500 text-black font-bold font-mono text-sm uppercase tracking-widest transition-all technical-border shadow-[0_0_20px_rgba(34,211,238,0.3)]">
                    <i data-lucide="download" class="inline w-4 h-4 mr-2"></i> Acquire Data
                </a>
            </div>
        </div>

        <div class="absolute inset-0 bg-gradient-to-t from-slate-900 to-transparent pointer-events-none"></div>
    </section>

    <section class="py-24 border-t border-slate-800 bg-slate-900/50">
        <div class="container mx-auto px-6 grid md:grid-cols-2 gap-16 items-center">
            
            <div class="relative technical-border p-8 h-80 flex items-center justify-center bg-slate-950">
                <div class="absolute top-2 left-2 text-xs text-slate-500 font-mono">ASSET_ID: AUTHOR_PORTRAIT</div>
                <div class="absolute bottom-2 right-2 text-xs text-red-500 font-mono">ERROR: 404 IMAGE NOT FOUND</div>
                
                <div class="w-32 h-40 border-2 border-slate-700 rounded-full flex flex-col items-center justify-center gap-2 relative">
                    <div class="w-24 h-px bg-slate-700 absolute top-10"></div>
                    <div class="w-24 h-px bg-slate-700 absolute top-20"></div>
                    <div class="w-2 h-2 bg-slate-700 rounded-full"></div>
                    <div class="text-[10px] text-slate-600 font-mono mt-4">PROCESSING...</div>
                </div>
                
                <div class="absolute top-1/4 right-1/4 w-3 h-3 bg-cyan-500 rounded-full animate-ping"></div>
                <div class="absolute bottom-1/3 left-1/4 w-2 h-2 bg-orange-500 rounded-full"></div>
            </div>

            <div>
                <h2 class="text-sm text-cyan-400 font-bold tracking-widest mb-2 uppercase">The Architect</h2>
                <h3 class="text-3xl font-bold mb-6">Built with Vectors, Not Paint</h3>
                <div class="prose prose-invert text-slate-400 font-mono text-sm leading-relaxed">
                    <p class="mb-4">
                        <span class="text-white">> AUTHOR NOTE:</span> As an author with <strong>aphantasia</strong>, I do not see images in my mind. I cannot visualize a dragon; I can only process the <em>concept</em> of a dragon (flying lizard, fire breath, hoarding tendency).
                    </p>
                    <p class="mb-4">
                        This world was built through semantic tension and engineering logic. The novel is not a painting; it is a schematic.
                    </p>
                    <p>
                        Arthur Penhaligon does not see the world as a movie. He hears the <span class="text-orange-400">friction</span> of a lie. He feels the <span class="text-cyan-400">weight</span> of history. He is debugging reality, one line of code at a time.
                    </p>
                </div>
            </div>

        </div>
    </section>

    <section class="py-24 container mx-auto px-6">
        <div class="flex items-end justify-between mb-12 border-b border-slate-800 pb-4">
            <div>
                <h2 class="text-3xl font-bold">Asset Registry: Oakhaven</h2>
                <p class="text-slate-500 font-mono text-xs mt-2">SECTOR 7G // LOCALIZED DISTORTION FIELD</p>
            </div>
            <div class="text-right hidden md:block">
                <div class="text-xs text-slate-500">LAST AUDIT:</div>
                <div class="text-cyan-400 font-mono">TUESDAY (PRE-EVENT)</div>
            </div>
        </div>

        <div class="grid md:grid-cols-3 gap-6">
            
            <div class="bg-slate-900 border border-slate-800 p-6 hover:border-cyan-500/50 transition-colors group">
                <div class="flex justify-between items-start mb-4">
                    <div class="w-10 h-10 border border-slate-700 flex items-center justify-center text-slate-500 group-hover:text-cyan-400 group-hover:border-cyan-400 transition-all">
                        <i data-lucide="coffee"></i>
                    </div>
                    <span class="text-[10px] bg-green-900/30 text-green-400 px-2 py-1 rounded">RECALIBRATED</span>
                </div>
                <h4 class="font-bold text-lg mb-2">The Kettle</h4>
                <p class="text-xs text-slate-400 font-mono leading-relaxed">
                    Former source of semantic noise. Previously claimed water was boiling at 60°C. Following acid treatment and Zero-Shot logic application, appliance now operates at 100% honesty.
                </p>
            </div>

            <div class="bg-slate-900 border border-slate-800 p-6 hover:border-orange-500/50 transition-colors group">
                <div class="flex justify-between items-start mb-4">
                    <div class="w-10 h-10 border border-slate-700 flex items-center justify-center text-slate-500 group-hover:text-orange-400 group-hover:border-orange-400 transition-all">
                        <i data-lucide="sprout"></i>
                    </div>
                    <span class="text-[10px] bg-orange-900/30 text-orange-400 px-2 py-1 rounded">UNSTABLE</span>
                </div>
                <h4 class="font-bold text-lg mb-2">Mrs. Higgins' Marrow</h4>
                <p class="text-xs text-slate-400 font-mono leading-relaxed">
                    Vegetable matter exhibiting unusual density. Initial scans suggest it is not growing via photosynthesis, but via <span class="text-white">Pure Spite</span>. Structural failure imminent upon emotional resolution.
                </p>
            </div>

            <div class="bg-slate-900 border border-slate-800 p-6 hover:border-red-500/50 transition-colors group">
                <div class="flex justify-between items-start mb-4">
                    <div class="w-10 h-10 border border-slate-700 flex items-center justify-center text-slate-500 group-hover:text-red-400 group-hover:border-red-400 transition-all">
                        <i data-lucide="home"></i>
                    </div>
                    <span class="text-[10px] bg-red-900/30 text-red-400 px-2 py-1 rounded">RENDER ERROR</span>
                </div>
                <h4 class="font-bold text-lg mb-2">Vane Architecture</h4>
                <p class="text-xs text-slate-400 font-mono leading-relaxed">
                    3D-printed housing unit. Lacks "Semantic Weight." Object has zero friction coefficient with reality. Warning: May float away in high winds of truth.
                </p>
            </div>

        </div>
    </section>

    <section id="read" class="py-24 bg-black border-y border-slate-800">
        <div class="container mx-auto px-6 max-w-4xl">
            
            <div class="flex items-center gap-2 mb-6">
                <div class="w-3 h-3 rounded-full bg-red-500"></div>
                <div class="w-3 h-3 rounded-full bg-yellow-500"></div>
                <div class="w-3 h-3 rounded-full bg-green-500"></div>
                <span class="ml-4 font-mono text-xs text-slate-500">/usr/bin/Arthur/logs/Chapter_01.txt</span>
            </div>

            <div class="bg-slate-900/50 border border-slate-800 p-8 md:p-12 font-mono text-sm md:text-base leading-loose shadow-2xl relative overflow-hidden">
                
                <div class="absolute top-0 right-0 p-4 opacity-10 pointer-events-none">
                    <i data-lucide="cpu" class="w-64 h-64"></i>
                </div>

                <div class="text-slate-300 relative z-10">
                    <p class="mb-6 text-cyan-500">>> INITIALIZING NARRATIVE PROTOCOL...</p>
                    <p class="mb-6 text-cyan-500">>> LOADING CHAPTER ONE...</p>
                    
                    <h3 class="text-2xl font-bold text-white mb-8">I. The Signal-to-Noise Ratio</h3>
                    
                    <p class="mb-6">
                        The Universe is not a composition; it is feedback.
                    </p>
                    <p class="mb-6">
                        It does not begin with a melodic hum. It begins with the screech of an ungrounded amplifier, a sprawling, uncontrolled explosion of data that has spent the subsequent fourteen billion years trying to find a ground wire.
                    </p>
                    <p class="mb-6">
                        If you listen to the cosmos—really listen, past the romantic static of the poets and the smoothed-over JPEGs of the astronomers—you do not hear a symphony. You hear the ambient roar of a celestial warehouse run by an absentee landlord who has lost the inventory list and is hoping the auditors don't notice the smell of burning hydrogen.
                    </p>
                    <p class="mb-6">
                        There are stars that burn with the frantic, desperate energy of a lightbulb realizing it is about to die. There are black holes that sit in the center of galaxies like cosmic plugholes, dragging light and time into a singularity of infinite density just to keep the floor clean.
                    </p>
                    <p class="mb-6">
                        And then, buried under layers of interstellar dust and administrative negligence, there is the Solar System. It is a neighborhood defined by clutter.
                    </p>

                    <div class="my-8 border-l-2 border-orange-500 pl-4 py-2 bg-orange-900/10 italic text-slate-400">
                        > SYSTEM NOTE: Arthur Penhaligon is a structural engineer. He wears heavy wool trousers and cardigans that smell of solder flux. He just wants a kettle that doesn't lie.
                    </div>

                    <p class="mb-6">
                        "You," Arthur said to the appliance, "are a hallucination."
                        <br><br>
                        The kettle sat on the workbench. It was white plastic, stained with the tea of a thousand mornings. It was a Boil-Master 3000, a name that promised a mastery of thermodynamics that the device clearly lacked.
                        <br><br>
                        "You clicked," Arthur accused. "The switch went clunk. But I have tested it. Sixty degrees Celsius. That is not tea water. That is a lukewarm deception."
                    </p>

                    <div class="mt-12 p-4 border border-red-500/30 bg-red-900/10 text-center">
                        <p class="text-red-500 font-bold mb-2">>> FATAL ERROR: TRIAL_LIMIT_REACHED</p>
                        <p class="text-slate-500 text-xs mb-4">ACCESS TO CHAPTERS 2-54 DENIED by THE FOREMAN.</p>
                        <p class="text-slate-400">"Hey! No free rides on the bandwidth, kid. You want to see the explosion? You want to see the bus that runs on regret? Buy the ticket."</p>
                    </div>

                </div>
            </div>
        </div>
    </section>

    <section id="buy" class="py-24 relative overflow-hidden">
        <div class="absolute -right-20 top-20 w-96 h-96 bg-cyan-500/10 rounded-full blur-3xl"></div>

        <div class="container mx-auto px-6 text-center relative z-10">
            <h2 class="text-5xl md:text-6xl font-bold mb-8">Debug Your Reality</h2>
            <p class="text-xl text-slate-400 max-w-2xl mx-auto mb-12">
                Get the full diagnostic manual. 54 Chapters. Zero lies. One very angry holographic foreman.
            </p>

            <div class="grid md:grid-cols-2 gap-8 max-w-4xl mx-auto">
                <div class="technical-border bg-slate-900 p-8 hover:bg-slate-800 transition-all group cursor-pointer">
                    <h3 class="text-2xl font-bold text-white mb-2">Digital Download</h3>
                    <div class="text-4xl font-bold text-cyan-400 mb-6">$9.99</div>
                    <ul class="text-left text-sm font-mono text-slate-400 mb-8 space-y-2">
                        <li class="flex items-center"><i data-lucide="check" class="w-4 h-4 mr-2 text-green-500"></i> .EPUB / .MOBI / .PDF</li>
                        <li class="flex items-center"><i data-lucide="check" class="w-4 h-4 mr-2 text-green-500"></i> High-Fidelity Text</li>
                        <li class="flex items-center"><i data-lucide="check" class="w-4 h-4 mr-2 text-green-500"></i> Foreman Commentary Track</li>
                    </ul>
                    <button class="w-full py-4 bg-cyan-600 group-hover:bg-cyan-500 text-black font-bold uppercase tracking-widest">
                        Initiate Transfer
                    </button>
                </div>

                <div class="technical-border bg-slate-900 p-8 opacity-75 grayscale relative">
                    <div class="absolute inset-0 flex items-center justify-center z-20">
                        <div class="bg-black border border-red-500 text-red-500 px-6 py-2 font-bold transform -rotate-12 text-2xl glitch" data-text="SOLD OUT">SOLD OUT</div>
                    </div>
                    <h3 class="text-2xl font-bold text-white mb-2">Physical Artifact</h3>
                    <div class="text-4xl font-bold text-slate-500 mb-6">$18.99</div>
                    <ul class="text-left text-sm font-mono text-slate-500 mb-8 space-y-2">
                        <li class="flex items-center"><i data-lucide="x" class="w-4 h-4 mr-2"></i> Paper (Organic)</li>
                        <li class="flex items-center"><i data-lucide="x" class="w-4 h-4 mr-2"></i> Heavy Mass</li>
                        <li class="flex items-center"><i data-lucide="x" class="w-4 h-4 mr-2"></i> Smells like ink</li>
                    </ul>
                    <button class="w-full py-4 bg-slate-800 text-slate-500 font-bold uppercase tracking-widest cursor-not-allowed">
                        Awaiting Restock
                    </button>
                </div>
            </div>
        </div>
    </section>

    <footer class="bg-slate-950 border-t border-slate-800 py-12 text-xs font-mono text-slate-600">
        <div class="container mx-auto px-6 flex flex-col md:flex-row justify-between items-center">
            <div>
                &copy; 2025 Arthur Penhaligon Engineering. All rights reserved.<br>
                Gravity is a registered trademark of The Universe.
            </div>
            <div class="mt-4 md:mt-0 flex gap-6">
                <a href="#" class="hover:text-cyan-400 transition-colors">System Log</a>
                <a href="#" class="hover:text-cyan-400 transition-colors">Patch Notes</a>
                <a href="#" class="hover:text-cyan-400 transition-colors">Contact Admin</a>
            </div>
        </div>
    </footer>

    <div id="foreman-interface" class="rounded-lg overflow-hidden technical-border">
        <div class="bg-slate-900 p-3 border-b border-slate-700 flex items-center justify-between">
            <div class="flex items-center gap-2">
                <div class="foreman-avatar rounded-sm">
                    <i data-lucide="hard-hat" class="w-5 h-5"></i>
                </div>
                <span class="font-bold text-cyan-400">THE FOREMAN</span>
            </div>
            <button id="close-foreman" class="text-slate-500 hover:text-white"><i data-lucide="x" class="w-3 h-3"></i></button>
        </div>
        <div class="p-4 h-24 flex items-center">
            <p id="foreman-text" class="text-slate-300 leading-snug">System scanning... user is idling. Inefficient.</p>
        </div>
        <div class="bg-slate-950 p-2 text-[10px] text-slate-600 text-right">
            STATUS: JUDGMENTAL
        </div>
    </div>

    <script>
        // 1. ICONS
        lucide.createIcons();

        // 2. SIGNAL TOGGLE LOGIC
        const toggle = document.getElementById('signal-toggle');
        const body = document.body;
        const statusText = document.getElementById('status-text');
        const statusIndicator = document.getElementById('status-indicator');
        const heroTitle = document.getElementById('hero-title');
        const heroLogline = document.getElementById('hero-logline');

        // Copy Variants
        const copy = {
            low: {
                title: "The Resonance of Tuesday",
                logline: "A charming story about a man who fixes kettles and finds friendship in a sleepy English village. Perfect for fans of light reading.",
                status: "SIGNAL: LOW",
                color: "text-orange-500",
                bg: "bg-orange-500"
            },
            high: {
                title: "THE RESONANCE OF TUESDAY",
                logline: "A structural engineer who can hear lies builds a machine to quiet his kettle and accidentally summons a holographic foreman to debug a universe running on faulty data.",
                status: "SIGNAL: HIGH_FIDELITY",
                color: "text-green-500",
                bg: "bg-green-500"
            }
        };

        toggle.addEventListener('change', function() {
            if(this.checked) {
                // High Fidelity Mode
                body.classList.add('high-fidelity');
                
                // Update Status Bar
                statusText.innerText = copy.high.status;
                statusText.className = `${copy.high.color} font-bold`;
                statusIndicator.className = `w-2 h-2 rounded-full ${copy.high.bg} animate-pulse`;

                // Update Hero Content (Zero-Shot Truth)
                heroTitle.innerText = copy.high.title;
                heroLogline.innerText = copy.high.logline;
                heroLogline.classList.remove('text-slate-400');
                heroLogline.classList.add('text-cyan-400');

                // Trigger Foreman Comment
                typeWriter("Finally! Someone turned the lights on. Look at those pixels! Sharp enough to cut yourself.");

            } else {
                // Low Fidelity Mode
                body.classList.remove('high-fidelity');
                
                // Update Status Bar
                statusText.innerText = copy.low.status;
                statusText.className = `${copy.low.color} font-bold`;
                statusIndicator.className = `w-2 h-2 rounded-full ${copy.low.bg} animate-pulse`;

                // Update Hero Content (Marketing Fluff)
                heroTitle.innerText = copy.low.title;
                heroLogline.innerText = copy.low.logline;
                heroLogline.classList.add('text-slate-400');
                heroLogline.classList.remove('text-cyan-400');
                
                // Trigger Foreman Comment
                typeWriter("Oh great. Back to the blur. Why do you prefer the lie? It's literally harder to read.");
            }
        });

        // 3. THE FOREMAN ENGINE
        const foremanInterface = document.getElementById('foreman-interface');
        const foremanText = document.getElementById('foreman-text');
        const closeForeman = document.getElementById('close-foreman');

        // Foreman Quotes Database
        const quotes = [
            "I'm monitoring your scroll speed. It's erratic. Have you had too much caffeine?",
            "Don't look at the 'Sold Out' sign. Look at the download button. It's lighter. Easier to carry.",
            "That toggle switch in the header? It's not a toy. Well, it is. But be careful.",
            "I see you hovering over the 'Buy' button. Commit to the click! Optimize your library!",
            "This website is built on a grid. Respect the grid."
        ];

        // Typewriter Effect
        function typeWriter(text) {
            foremanText.innerHTML = "";
            let i = 0;
            let speed = 30; 
            function type() {
                if (i < text.length) {
                    foremanText.innerHTML += text.charAt(i);
                    i++;
                    setTimeout(type, speed);
                }
            }
            type();
        }

        // Trigger Foreman on Load
        setTimeout(() => {
            foremanInterface.classList.add('active');
            typeWriter("System online. I'm The Foreman. I'm here to ensure you don't break the CSS.");
        }, 2000);

        // Close Foreman
        closeForeman.addEventListener('click', () => {
            foremanInterface.classList.remove('active');
        });

        // Trigger Random Quotes on Scroll (Debounced)
        let isScrolling;
        window.addEventListener('scroll', () => {
            window.clearTimeout(isScrolling);
            isScrolling = setTimeout(() => {
                if(Math.random() > 0.7 && foremanInterface.classList.contains('active')) {
                    const randomQuote = quotes[Math.floor(Math.random() * quotes.length)];
                    typeWriter(randomQuote);
                }
            }, 2000);
        });

    </script>
</body>
</html>
