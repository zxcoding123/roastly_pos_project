<script>
  const founders = [
    {
      name: "Ahmad",
      role: "AI Automation Architect, Full-stack Developer, System Designer and UI/UX Lead",
      bio: "Full-stack developer focused on resilient, local-first systems and high-end UI/UX. Specialist in AI automation and system design. Full-time Full-stack Mobile and Web Developer",
      image: "https://api.dicebear.com/7.x/avataaars/svg?seed=Ahmad" 
    },
    {
      name: "Fahad",
      role: "Full-stack Developer and Documentation Specialist",
      bio: "Specialist in robust backend architecture and seamless mobile integration. Business-minded full-stack developer with a focus on clear documentation and user-friendly design.",
      image: "https://api.dicebear.com/7.x/avataaars/svg?seed=Fahad" 
    }
  ];
</script>

<section id="founders" class="py-32 px-6 max-w-6xl mx-auto border-t border-white/5">
  <div class="text-center mb-20">
    <span class="text-blue-500 font-mono text-[10px] uppercase tracking-[0.4em] mb-4 block" id="founders">The Founders</span>
    <h2 class="text-4xl md:text-5xl font-bold tracking-tighter text-white mb-6">Built by humans, <br /><span class="text-zinc-600 italic">not a corporation.</span></h2>
    <p class="text-zinc-500 text-lg max-w-2xl mx-auto leading-relaxed">
      We’re independent developers from Zamboanga City. We don't believe in "one-size-fits-all" software. We build tools that work for the local rhythm of our community.
    </p>
  </div>

  <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
    {#each founders as founder (founder.name)}
      <div class="glass-card p-10 flex flex-col md:flex-row items-center gap-8 group hover:bg-white/[0.02] transition-all duration-500">
        <div class="relative shrink-0">
          <div class="absolute -inset-2 bg-blue-500/20 rounded-full blur-xl opacity-0 group-hover:opacity-100 transition-opacity duration-700"></div>
          <div class="w-32 h-32 rounded-2xl bg-zinc-900 border border-white/10 overflow-hidden grayscale group-hover:grayscale-0 transition-all duration-700">
            <img src={founder.image} alt={founder.name} class="w-full h-full object-cover" />
          </div>
        </div>

        <div class="text-center md:text-left">
          <h4 class="text-2xl font-bold text-white tracking-tight">{founder.name}</h4>
          <p class="text-blue-500 font-mono text-[10px] uppercase tracking-widest mb-4">{founder.role}</p>
          <p class="text-zinc-500 text-sm leading-relaxed max-w-xs">
            {founder.bio}
          </p>
        </div>
      </div>
    {/each}
  </div>

  <div class="mt-16 p-8 bg-white/[0.02] border border-white/5 rounded-3xl flex flex-col md:flex-row justify-between items-center gap-8">
    <div class="flex items-center gap-6">
      <div class="w-12 h-12 rounded-full bg-emerald-500/10 border border-emerald-500/20 flex items-center justify-center text-emerald-500">
        ✓
      </div>
      <div>
        <p class="text-white font-bold text-sm">Direct Support</p>
        <p class="text-zinc-500 text-xs">No bots. You get our personal contact numbers for 24/7 technical assistance.</p>
      </div>
    </div>
    <div class="h-px w-full md:w-px md:h-12 bg-white/10"></div>
    <div class="flex items-center gap-6">
      <div class="w-12 h-12 rounded-full bg-blue-500/10 border border-blue-500/20 flex items-center justify-center text-blue-500">
        ⚡
      </div>
      <div>
        <p class="text-white font-bold text-sm">Custom Tailored</p>
        <p class="text-zinc-500 text-xs">Need a specific feature for your coffee shop? We can build it into your deployment.</p>
      </div>
    </div>
  </div>
</section>