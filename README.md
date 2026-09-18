<
        if (dot.y < 0 || dot.y > canvas.height) dot.vy *= -1;
!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Nicolas Ledezma - Terminal Profile</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Fira+Code:wght@400;500;700&display=swap');

    body {
      font-family: 'Fira Code', monospace;
      background-color: #0b0f19;
      color: #94a3b8;
    }

    /* Glassmorphism & Neon Glow */
    .terminal-card {
      background: rgba(15, 23, 42, 0.85);
      backdrop-filter: blur(12px);
      border: 1px solid rgba(56, 189, 248, 0.2);
      box-shadow: 0 0 25px rgba(56, 189, 248, 0.08),
                  inset 0 0 15px rgba(56, 189, 248, 0.03);
    }

    .neon-text-cyan {
      color: #38bdf8;
      text-shadow: 0 0 8px rgba(56, 189, 248, 0.5);
    }

    .neon-text-pink {
      color: #f43f5e;
      text-shadow: 0 0 8px rgba(244, 63, 94, 0.5);
    }

    .neon-border {
      border-color: rgba(56, 189, 248, 0.3);
    }

    .border-glow:hover {
      border-color: rgba(56, 189, 248, 0.6);
      box-shadow: 0 0 15px rgba(56, 189, 248, 0.25);
    }

    /* Custom Scrollbar */
    ::-webkit-scrollbar {
      width: 6px;
    }
    ::-webkit-scrollbar-track {
      background: #0f172a;
    }
    ::-webkit-scrollbar-thumb {
      background: #1e293b;
      border-radius: 3px;
    }
    ::-webkit-scrollbar-thumb:hover {
      background: #38bdf8;
    }
  </style>
</head>
<body class="min-h-screen flex items-center justify-center p-4">

  <div class="w-full max-w-4xl terminal-card rounded-xl overflow-hidden shadow-2xl">
    
    <!-- Terminal Header Bar -->
    <div class="bg-slate-900/90 px-4 py-3 border-b border-slate-800 flex items-center justify-between">
      <div class="flex items-center space-x-2">
        <div class="w-3 h-3 rounded-full bg-red-500/80 hover:bg-red-500 transition-colors"></div>
        <div class="w-3 h-3 rounded-full bg-yellow-500/80 hover:bg-yellow-500 transition-colors"></div>
        <div class="w-3 h-3 rounded-full bg-green-500/80 hover:bg-green-500 transition-colors"></div>
        <span class="text-xs text-slate-400 font-medium ml-3 sm:inline hidden">profile.sh --live</span>
      </div>

      <div class="flex items-center space-x-3 text-xs">
        <span class="flex items-center text-emerald-400 font-semibold">
          <span class="w-2 h-2 rounded-full bg-emerald-400 animate-ping mr-2"></span>
          LIVE
        </span>
        <span class="bg-slate-800 px-2.5 py-1 rounded text-cyan-400 font-mono border border-cyan-500/20">
          @Nicolasledezma
        </span>
      </div>
    </div>

    <!-- Main Content Body -->
    <div class="p-6 grid grid-cols-1 md:grid-cols-12 gap-6 items-center">
      
      <!-- Visual Map Side (Left Column) -->
      <div class="md:col-span-5 flex flex-col items-center justify-center p-4 rounded-lg bg-slate-950/60 border border-slate-800/80 relative overflow-hidden group">
        <div class="absolute inset-0 bg-gradient-to-b from-cyan-500/5 to-transparent pointer-events-none"></div>
        
        <span class="text-xs font-mono text-cyan-400/70 self-start mb-2 tracking-widest">VISUAL.MAP</span>
        
        <!-- Interactive Canvas Logo / ASCII Animation -->
        <canvas id="asciiCanvas" width="200" height="200" class="my-2 cursor-pointer"></canvas>

        <div class="w-full flex justify-between text-[10px] text-slate-500 font-mono mt-2">
          <span>PTS 18000</span>
          <span>FS/SERPENTINE</span>
        </div>
      </div>

      <!-- System Info Side (Right Column) -->
      <div class="md:col-span-7 space-y-2 text-xs sm:text-sm">
        <div class="text-cyan-400 font-bold tracking-wider text-sm mb-4 border-b border-slate-800 pb-2 flex justify-between items-center">
          <span>SYSTEM.INFO</span>
          <span class="text-[10px] text-slate-500 font-normal">v2.4.0</span>
        </div>

        <div class="grid grid-cols-12 gap-y-2.5 font-mono">
          <div class="col-span-4 text-slate-500">Subject</div>
          <div class="col-span-8 text-slate-200 font-semibold">Nicolas Ledezma</div>

          <div class="col-span-4 text-slate-500">Role</div>
          <div class="col-span-8 text-cyan-300 font-medium">Frontend Dev · UI/UX Designer</div>

          <div class="col-span-4 text-slate-500">Location</div>
          <div class="col-span-8 text-slate-300">Venezuela</div>

          <div class="col-span-4 text-slate-500">Status</div>
          <div class="col-span-8 text-emerald-400">Building + Learning + Shipping</div>

          <div class="col-span-4 text-slate-500">ToolChain</div>
          <div class="col-span-8 text-slate-300">Cursor · VS Code · Git · Figma</div>

          <div class="col-span-4 text-slate-500">Core.Lang</div>
          <div class="col-span-8 text-rose-400">TypeScript · JavaScript · Dart</div>

          <div class="col-span-4 text-slate-500">Core.Frontend</div>
          <div class="col-span-8 text-sky-300">React · Flutter · Tailwind CSS</div>

          <div class="col-span-4 text-slate-500">Core.Backend</div>
          <div class="col-span-8 text-purple-400">Supabase · Node.js · Vite</div>

          <div class="col-span-4 text-slate-500">Grid.LinkedIn</div>
          <div class="col-span-8">
            <a href="https://linkedin.com/in/nicolasledezma" target="_blank" class="text-cyan-400 hover:underline hover:text-cyan-300 transition-colors">
              /in/nicolasledezma
            </a>
          </div>

          <div class="col-span-4 text-slate-500">Grid.GitHub</div>
          <div class="col-span-8">
            <a href="https://github.com/Nicolasledezma" target="_blank" class="text-cyan-400 hover:underline hover:text-cyan-300 transition-colors">
              Nicolasledezma
            </a>
          </div>
        </div>
      </div>

    </div>

    <!-- Terminal Footer -->
    <div class="bg-slate-900/60 px-6 py-3 border-t border-slate-800/80 flex flex-wrap items-center justify-between text-[11px] text-slate-500 font-mono">
      <div class="flex items-center space-x-2">
        <span class="w-2 h-2 rounded-full bg-cyan-400 animate-pulse"></span>
        <span class="text-cyan-400">ALL SYSTEMS NOMINAL</span>
      </div>
      <div>UTC-4 · LATAM NODE</div>
    </div>

  </div>

  <script>
    // Particle matrix animation in Visual Map canvas
    const canvas = document.getElementById('asciiCanvas');
    const ctx = canvas.getContext('2d');

    const dots = [];
    const numDots = 80;

    for (let i = 0; i < numDots; i++) {
      dots.push({
        x: Math.random() * canvas.width,
        y: Math.random() * canvas.height,
        vx: (Math.random() - 0.5) * 0.8,
        vy: (Math.random() - 0.5) * 0.8,
        radius: Math.random() * 1.5 + 0.5
      });
    }

    function animate() {
      ctx.clearRect(0, 0, canvas.width, canvas.height);

      // Draw code tag symbol in middle
      ctx.fillStyle = 'rgba(56, 189, 248, 0.15)';
      ctx.font = 'bold 36px "Fira Code", monospace';
      ctx.textAlign = 'center';
      ctx.fillText('< / >', canvas.width / 2, canvas.height / 2 + 10);

      // Render dots & lines
      ctx.fillStyle = '#38bdf8';
      dots.forEach((dot, index) => {
        dot.x += dot.vx;
        dot.y += dot.vy;

        if (dot.x < 0 || dot.x > canvas.width) dot.vx *= -1;
        ctx.beginPath();
        ctx.arc(dot.x, dot.y, dot.radius, 0, Math.PI * 2);
        ctx.fill();
`
        // Connect nearby dots
        for (let j = index + 1; j < dots.length; j++) {
          const other = dots[j];
          const dist = Math.hypot(dot.x - other.x, dot.y - other.y);
          if (dist < 40) {
            ctx.strokeStyle = `rgba(56, 189, 248, ${0.3 - dist / 130})`;
            ctx.lineWidth = 0.5;
            ctx.beginPath();
            ctx.moveTo(dot.x, dot.y);
            ctx.lineTo(other.x, other.y);
            ctx.stroke();
          }
        }
      });

      requestAnimationFrame(animate);
    }

    animate();
  </script>
</body>
</html>
