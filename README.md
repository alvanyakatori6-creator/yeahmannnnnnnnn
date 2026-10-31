index.html<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Base-27 Omni-Trinity Engine</title>
    <script src="https://tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        .custom-scrollbar::-webkit-scrollbar { width: 4px; height: 4px; }
        .custom-scrollbar::-webkit-scrollbar-track { background: #0f172a; }
        .custom-scrollbar::-webkit-scrollbar-thumb { background: #334155; border-radius: 2px; }
    </style>
</head>
<body class="bg-slate-950 text-slate-100 font-sans antialiased p-4 h-screen flex flex-col justify-between overflow-hidden">

    <!-- Header -->
    <header class="border border-slate-800 bg-slate-950/90 rounded-2xl p-5 mb-4 shadow-2xl flex flex-wrap items-center justify-between gap-4 shrink-0">
        <div class="flex items-center space-x-3">
            <div class="w-3 h-3 rounded-full bg-red-500 animate-ping"></div>
            <div class="w-3 h-3 rounded-full bg-emerald-500 animate-pulse"></div>
            <div class="w-3 h-3 rounded-full bg-blue-500 animate-pulse"></div>
            <div>
                <h1 class="text-base font-mono font-bold tracking-wider text-slate-100">BASE-27 OMNI-TRINITY ENGINE</h1>
                <p class="text-xs text-slate-400 font-mono">Unified Synthesis: Quantum Physics, Light Spectrum, Sacred Canon & Audio Harmonics</p>
            </div>
        </div>
        <div class="flex items-center space-x-3">
            <button id="masterAudioBtn" class="bg-cyan-600 hover:bg-cyan-500 text-white px-4 py-2 rounded-xl text-xs font-mono font-bold transition-all shadow-lg flex items-center space-x-2">
                <i class="fa-solid fa-volume-high"></i>
                <span id="audioStatus">Audio: Enabled</span>
            </button>
            <button id="resetEngineBtn" class="bg-slate-800 hover:bg-slate-700 text-slate-300 px-4 py-2 rounded-xl text-xs font-mono font-bold transition-all">
                <i class="fa-solid fa-rotate-left mr-1"></i> Reset
            </button>
        </div>
    </header>

    <!-- Main Workspace Grid -->
    <div class="grid grid-cols-1 lg:grid-cols-3 gap-4 flex-1 overflow-hidden">
        
        <!-- Left Panel: Base-27 Selector & Quick Controls -->
        <div class="bg-slate-950/80 border border-slate-800 rounded-2xl p-5 flex flex-col space-y-4">
            <div class="flex justify-between items-center border-b border-slate-800 pb-3">
                <span class="text-xs font-mono font-bold text-slate-400 uppercase tracking-widest">Base-27 Node Array (3³)</span>
                <span id="activeNodeBadge" class="text-xs font-mono px-2.5 py-1 rounded bg-pink-500/20 text-pink-400 border border-pink-500/30 font-bold">Node 1 / 27</span>
            </div>

            <!-- 27 Grid Buttons -->
            <div id="base27Grid" class="grid grid-cols-3 gap-1.5 flex-1 overflow-y-auto custom-scrollbar p-1 bg-slate-900/50 rounded-xl border border-slate-800">
                <!-- Injected via JS -->
            </div>

            <div class="bg-slate-900/80 border border-slate-800 rounded-xl p-4 space-y-2 text-xs font-mono">
                <div class="text-slate-400 font-bold">Trinitarian Pivot Navigation</div>
                <div class="flex justify-between text-slate-300"><span>Root Axis (1-9):</span><span class="text-red-400">Matter & Thermal</span></div>
                <div class="flex justify-between text-slate-300"><span>Mediating Axis (10-18):</span><span class="text-emerald-400">Bio-Spectral Flux</span></div>
                <div class="flex justify-between text-slate-300"><span>Cosmic Apex (19-27):</span><span class="text-blue-400">Quantum Transcendence</span></div>
            </div>
        </div>

        <!-- Center & Right Panel: Deep Encyclopedic Interconnection & Spectrum Display -->
        <div class="lg:col-span-2 bg-slate-950/80 border border-slate-800 rounded-2xl p-5 flex flex-col justify-between space-y-4">
            
            <!-- Node Detail Inspector -->
            <div class="space-y-4">
                <div class="flex items-center justify-between border-b border-slate-800 pb-3">
                    <div class="flex items-center space-x-2">
                        <i class="fa-solid fa-atom text-cyan-400"></i>
                        <h2 id="nodeTitle" class="text-sm font-mono font-bold text-slate-200">Node 1: Alpha Genesis & Hydrogen Ground</h2>
                    </div>
                    <span id="nodeSpectrum" class="text-[11px] font-mono px-2.5 py-1 rounded bg-red-950/40 text-red-400 border border-red-900/50">656.3 nm (Balmer Red)</span>
                </div>

                <div class="grid grid-cols-1 md:grid-cols-2 gap-4 text-xs font-mono">
                    <div class="bg-slate-900/60 border border-slate-800/80 rounded-xl p-3.5 space-y-2">
                        <div class="text-slate-400 font-bold uppercase tracking-wide text-[10px]">Empirical & Quantum Metrics</div>
                        <div><strong class="text-slate-500">Frequency:</strong> <span id="nodeFreq" class="text-cyan-300">440.0 Hz</span></div>
                        <div><strong class="text-slate-500">Temperature:</strong> <span id="nodeTemp" class="text-amber-400">4,415 K (Thermal Plasma)</span></div>
                        <div><strong class="text-slate-500">Quantum State:</strong> <span id="nodeQuantum" class="text-slate-300">Ground Orbital n=3</span></div>
                    </div>

                    <div class="bg-slate-900/60 border border-slate-800/80 rounded-xl p-3.5 space-y-2">
                        <div class="text-slate-400 font-bold uppercase tracking-wide text-[10px]">Universal Canon & Geometry</div>
                        <div><strong class="text-slate-500">Sacred Geometry:</strong> <span id="nodeGeometry" class="text-pink-300">Point / Monad</span></div>
                        <div><strong class="text-slate-500">Philosophical Canon:</strong> <span id="nodeCanon" class="text-emerald-300">Creation / Fiat Lux</span></div>
                        <div><strong class="text-slate-500">Cosmic Dimension:</strong> <span id="nodeDimension" class="text-blue-300">3D Spacetime Base</span></div>
                    </div>
                </div>

                <!-- Detailed Explanation / Totality Bridge -->
                <div class="bg-slate-900/40 border border-slate-800 rounded-xl p-4 text-xs font-mono text-slate-300 leading-relaxed">
                    <span class="text-cyan-400 font-bold">Total Interconnection Synthesis:</span>
                    <p id="nodeDescription" class="mt-1 text-slate-400">
                        Initializing complete unified mapping across all canonical structures, light spectra, and acoustic frequencies. Click any node in the Base-27 matrix to instantly synchronize all levels of reality.
                    </p>
                </div>
            </div>

            <!-- Visualizer Bar -->
            <div class="border-t border-slate-800 pt-4 flex flex-col sm:flex-row items-center justify-between gap-3 text-xs font-mono text-slate-500">
                <div class="flex items-center space-x-2">
                    <span class="w-2 h-2 rounded-full bg-emerald-400 animate-ping"></span>
                    <span>Base-27 Harmonic Engine Fully Active</span>
                </div>
                <div class="text-right text-[11px]">
                    Unified Totality Matrix • Air-Tight & Uncontradictable Logic
                </div>
            </div>

        </div>
    </div>

    <script>
        const nodesData = Array.from({ length: 27 }, (_, i) => {
            const id = i + 1;
            const spectra = ["656.3 nm (Balmer Red)", "486.1 nm (Cyan Line)", "434.1 nm (Blue Line)", "589.0 nm (Sodium D)", "532.0 nm (Green Laser)"];
            const temps = [4415, 5961, 6675, 5778, 6000];
            const geometries = ["Monad / Point", "Vesica Piscis", "Seed of Life", "Tree of Life (Keter)", "Metatron Cube", "Sri Yantra Bindu", "Flower of Life", "Merkaba Star", "Platonic Icosahedron"];
            const canons = ["Genesis Fiat Lux", "Logos Principle", "Trinitarian Pivot", "Solfeggio Harmony", "Cosmic Order", "Divine Resonance", "Absolute Infinity"];
            
            return {
                id: id,
                title: `Node ${id}: Universal Pivot Level ${Math.ceil(id / 3)}`,
                freq: (220 + (id * 18.5)).toFixed(1),
                spectrum: spectra[id % spectra.length],
                temp: temps[id % temps.length] + (id * 35),
                geometry: geometries[id % geometries.length],
                canon: canons[id % canons.length],
                dimension: `${(id % 9) + 3}-Dimensional Holographic Manifold`,
                desc: `Node ${id} integrates foundational quantum waveforms with macrocosmic sacred geometries. Operating under Base-27 harmonic resonance (3³), this node bridges thermodynamic light emission with universal philosophical canon.`
            };
        });

        let activeNode = 1;
        let audioEnabled = true;
        let audioCtx = null;

        function initAudio() {
            if (!audioCtx) audioCtx = new (window.AudioContext || window.webkitAudioContext)();
        }

        function playNodeTone(freq) {
            if (!audioEnabled) return;
            initAudio();
            try {
                let osc = audioCtx.createOscillator();
                let gain = audioCtx.createGain();
                osc.type = 'sine';
                osc.frequency.setValueAtTime(parseFloat(freq), audioCtx.currentTime);
                gain.gain.setValueAtTime(0.1, audioCtx.currentTime);
                gain.gain.exponentialRampToValueAtTime(0.001, audioCtx.currentTime + 0.6);
                osc.connect(gain);
                gain.connect(audioCtx.destination);
                osc.start();
                osc.stop(audioCtx.currentTime + 0.6);
            } catch (e) {
                console.log("Audio context waiting for user gesture.");
            }
        }

        function renderGrid() {
            const grid = document.getElementById('base27Grid');
            grid.innerHTML = '';
            nodesData.forEach(node => {
                const btn = document.createElement('button');
                const isActive = node.id === activeNode;
                btn.className = `p-2.5 rounded-xl text-xs font-mono font-bold transition-all flex flex-col items-center justify-center border ${
                    isActive 
                        ? 'bg-cyan-600/30 text-cyan-300 border-cyan-400 shadow-lg scale-105' 
                        : 'bg-slate-900 hover:bg-slate-800 text-slate-300 border-slate-800'
                }`;
                btn.innerHTML = `<span class="text-[10px] text-slate-500">N-${node.id}</span><span>#${node.id}</span>`;
                btn.onclick = () => {
                    activeNode = node.id;
                    updateUI();
                    playNodeTone(node.freq);
                };
                grid.appendChild(btn);
            });
        }

        function updateUI() {
            const data = nodesData[activeNode - 1];
            document.getElementById('activeNodeBadge').innerText = `Node ${activeNode} / 27`;
            document.getElementById('nodeTitle').innerText = data.title;
            document.getElementById('nodeSpectrum').innerText = data.spectrum;
            document.getElementById('nodeFreq').innerText = `${data.freq} Hz`;
            document.getElementById('nodeTemp').innerText = `${data.temp.toLocaleString()} K`;
            document.getElementById('nodeQuantum').innerText = `Harmonic Wave Vector n=${(activeNode % 5) + 2}`;
            document.getElementById('nodeGeometry').innerText = data.geometry;
            document.getElementById('nodeCanon').innerText = data.canon;
            document.getElementById('nodeDimension').innerText = data.dimension;
            document.getElementById('nodeDescription').innerText = data.desc;
            renderGrid();
        }

        document.getElementById('masterAudioBtn').onclick = () => {
            audioEnabled = !audioEnabled;
            const btn = document.getElementById('masterAudioBtn');
            const status = document.getElementById('audioStatus');
            if (audioEnabled) {
                status.innerText = "Audio: Enabled";
                btn.className = "bg-cyan-600 hover:bg-cyan-500 text-white px-4 py-2 rounded-xl text-xs font-mono font-bold transition-all shadow-lg flex items-center space-x-2";
            } else {
                status.innerText = "Audio: Muted";
                btn.className = "bg-slate-800 hover:bg-slate-700 text-slate-400 px-4 py-2 rounded-xl text-xs font-mono font-bold transition-all flex items-center space-x-2";
            }
        };

        document.getElementById('resetEngineBtn').onclick = () => {
            activeNode = 1;
            updateUI();
        };

        renderGrid();
        updateUI();
    </script>
</body>
</html>
