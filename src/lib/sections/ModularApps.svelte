<script>
  const apps = [
    {
      name: "Point of Sale",
      target: "Front of House",
      description: "The core engine for order taking. Built for speed, offline reliability, and local WebSocket synchronization.",
      tech: "Flutter + Isar + SQLite",
      features: ["Offline Ordering", "Real-time Sync", "Revenue Management", "Save Receipts"],
      gradient: "from-blue-500/20",
      size: "col-span-1"
    },
    {
      name: "Barista Display",
      target: "The Bar",
      description: "The central nervous system. This device hosts the local database and manages all incoming orders.",
      tech: "Flutter + WebSockets + Bonsoir",
      features: ["Central System Host", "Live Queue", "Status Toggles", "Performance Tracking"],
      gradient: "from-emerald-500/20",
      size: "col-span-1"
    },
    {
      name: "Order Taker",
      target: "Floor Staff",
      description: "A lightweight mobile satellite. Take orders at the table and receive instant haptic pings when drinks are ready.",
      tech: "Flutter + WebSockets",
      features: ["Instant Transmission", "Ready Notifications", "Mobile Optimized UI", "Table Management"],
      gradient: "from-blue-400/10",
      size: "col-span-1"
    },
    {
      name: "Admin Console",
      target: "The Office",
      locked: true,
      description: "The brain of the operation. Manage multi-branch inventory, staff roles, and deep revenue analytics from anywhere in the world.",
      tech: "Svelte 5 + Cloud Integration",
      features: ["Inventory Control", "RBAC Management", "Financial Reports", "Multi-branch Sync"],
      gradient: "from-purple-500/20",
      size: "col-span-1 md:col-span-3" // This makes it take full width
    }
  ];
</script>

<section id="ecosystem" class="py-32 px-6 max-w-6xl mx-auto">
  <div class="flex flex-col md:flex-row justify-between items-end mb-16 gap-8">
    <div class="max-w-2xl">
      <h2 class="text-4xl md:text-6xl font-bold tracking-tighter text-white mb-6">
        Different Layers<br /><span class="text-zinc-600 italic">One Ecosystem.</span>
      </h2>
      <p class="text-zinc-400 text-lg leading-relaxed">
        We split the business logic into modular layers. This ensures that a busy kitchen never slows down the checkout, and your data remains secure and accessible.
      </p>
    </div>
    <div class="hidden md:block pb-2">
       <span class="text-[10px] font-mono uppercase tracking-[0.3em] text-zinc-500 rotate-90 origin-left">Architecture 1.0</span>
    </div>
  </div>

  <div class="grid grid-cols-1 md:grid-cols-3 gap-px bg-white/10 border border-white/10 rounded-3xl overflow-hidden shadow-2xl">
    {#each apps as app (app.name)}
      <div class="{app.size} bg-[#050505] p-10 group relative flex flex-col justify-between min-h-[400px] transition-colors overflow-hidden">
        
        {#if app.locked}
          <div class="absolute inset-0 z-20 backdrop-blur-[12px] bg-black/40 flex flex-col items-center justify-center border border-white/5">
            <div class="px-6 py-2 bg-white text-black text-[10px] font-black uppercase tracking-[0.4em] rounded-full shadow-[0_0_30px_rgba(255,255,255,0.2)]">
              Coming Soon
            </div>
          </div>
        {/if}

        <div class="absolute top-0 left-0 w-full h-full bg-gradient-to-br {app.gradient} to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-700"></div>
        
        <div class="relative z-10">
          <p class="text-[10px] font-bold uppercase tracking-widest text-blue-500 mb-2">{app.target}</p>
          <h3 class="text-2xl font-bold text-white mb-4 tracking-tight">{app.name}</h3>
          <p class="text-zinc-500 text-sm leading-relaxed mb-8 font-medium max-w-md">
            {app.description}
          </p>
          
          <ul class="grid grid-cols-1 sm:grid-cols-2 gap-3">
            {#each app.features as feature (feature)}
              <li class="flex items-center gap-3 text-xs text-zinc-400">
                <span class="w-1 h-1 bg-blue-500/50 rounded-full"></span>
                {feature}
              </li>
            {/each}
          </ul>
        </div>

        <div class="relative z-10 mt-12 pt-6 border-t border-white/5 flex justify-between items-center">
          <span class="text-[10px] font-mono text-zinc-600 uppercase tracking-widest">{app.tech}</span>
          <div class="flex items-center gap-2">
            {#if app.name === "Barista Display"}
              <span class="text-[9px] font-bold text-blue-500 uppercase tracking-tighter">System Host</span>
            {/if}
            <div class="w-2 h-2 rounded-full {app.name === 'Barista Display' ? 'bg-blue-500 shadow-[0_0_8px_#3b82f6]' : 'bg-white/10'}"></div>
          </div>
        </div>
      </div>
    {/each}
  </div>

  <div class="mt-20 pt-20 border-t border-white/5">
    <h2 class="text-4xl font-bold tracking-tighter text-white mb-4">The Cafe Core.</h2>
    <p class="text-zinc-500 text-lg leading-relaxed max-w-3xl">
      Modularity isn't just a buzzword. By separating the <b>Ordering</b> and <b>Brewing</b> logic, we ensure that neither side ever experiences lag. Even if your internet goes down, the local server on the Barista device keeps the orders flying.
    </p>
  </div>
</section>